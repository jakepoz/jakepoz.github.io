---
layout: post
title:  "RNN-T Speech Transcription in the Browser"
date:   2024-05-24 14:08:00 -0700
categories: research
---

### TL;DR
I made an RNN-T based speech recognition system that runs in the browser using TensorflowJS.

You can try the demo here: [https://rnnt.jakepoz.com/](https://rnnt.jakepoz.com/)

Fair warning: The quality ain't gonna make it up on any leaderboards okay? 

The full code is available here: [https://github.com/jakepoz/rnnt](https://github.com/jakepoz/rnnt)
 - Basic RNN-T architecture implemented cleanly from scratch
 - Jasper-like convolutional audio encoder for easy streaming
 - Simple streaming featurizer that works the same in PyTorch and TFJS.
 - Runs the entire model in the browser using the user's GPU.

### Background
There are many possible neural network architectures for transcribing speech into text and performing automatic speech recognition (ASR).
The most common architectures being trained today are the following:
  - CTC Loss [https://distill.pub/2017/ctc/](https://distill.pub/2017/ctc/)
  - RNN-T Loss [https://arxiv.org/pdf/1211.3711](https://arxiv.org/pdf/1211.3711)
  - Encoder-Decoder Transformers [https://cdn.openai.com/papers/whisper.pdf](https://cdn.openai.com/papers/whisper.pdf)

The challenge is that ASR is fundamentally a sequence-to-sequence problem,
but the sequences involved are of different lengths. The 
relationship between the length of the input and the length of the output is
not well-defined. You can have a 5-second clip of someone talking really fast that contains
30+ words. Or a 5-second clip with just 1-2 words in it.

This means that you can't just repeatedly classify fixed chunks of audio as characters/tokens/words,
you need to have a way to deal with slower and faster sequences.

Each of the architectures listed above has a different way of dealing with this problem.

### Streaming
A traditional transformer architecture needs to see the entire input before it can generate
the first token of output. And while a CTC network is more interesting 
(check out the link to how it works above), it usually has lower quality than the other methods,
requiring you to apply post-processing techniques such as language models to improve accuracy,
which can make it harder to work in a streaming fashion. 

Only one of the architectures above is well suited for streaming applications, the RNN-T.

You start by encoding the audio sequence using any neural network model you deem suitable.
In my case, I chose to use a convolutional-network, where the convolutions were padded to be casual.
This means that each encoded audio frame only sees information from the current frame, 
or previous frames, and not from any future frames. 
Other encoders such as RNNs are also suitable if you want to support streaming inference.

Then, you encode the text sequence in a similar fashion using a second neural network.

The key of the RNN-T then, is the "joint" network at the center. 

Consider the problem of mapping your encoded audio sequence and your encoded text sequence to one another as a
sequence "transduction". This basically means that you start by looking at the first audio frame, and
then first text frame (initialized from an empty string).

You then ask the joint network: "should I output a text token given my current audio frame and current text frame"?
If it says yes, then you take that text token, append it to the text context and ask the question again.
If it says no, then you output a so-called "blank" token and move onto the next audio frame without adding any text
to the context.

The beauty of this architecture, is that during training, the resulting text sequence is known, so you can consider
every possible path through a 2-D matrix of choices, and reduce that to a simple single loss using dynamic programming.

And if you chose your audio and text encoders to support streaming inference, you can run this algorithm at 
inference time, without having to see the whole input in advance.

### Key Components of the Code
- **[train.py](https://github.com/jakepoz/rnnt/blob/master/rnnt/train.py)**: Contains the training loop using PyTorch, supporting Hydra for configuration, DDP for multi-GPU training, and Tensorboard for logging.
- **[featurizer.py](https://github.com/jakepoz/rnnt/blob/master/rnnt/featurizer.py)**: Converts audio samples into spectrograms using FFT, a crucial step before feeding audio data into the encoder.
- **[dataset.py](https://github.com/jakepoz/rnnt/blob/master/rnnt/dataset.py)**: Manages datasets, specifically Mozilla's Common Voice and Librispeech.
- **[causalconv.py](https://github.com/jakepoz/rnnt/blob/master/rnnt/causalconv.py)**: Implements Conv1d layers that prevent the network from seeing future frames, essential for streaming.
- **[joint.py](https://github.com/jakepoz/rnnt/blob/master/rnnt/joint.py)**: The joint model is just a simple Linear layer. Any more complicated though, and the O(n^2) RNN-T loss function becomes intractable.
- **[jasper.py](https://github.com/jakepoz/rnnt/blob/master/rnnt/jasper.py)**: The audio encoder is based off of Jasper which involves many residual blocks of causal convolutions.


### Using TensorflowJS

I thought it would be fun to let you run this final network using [Tensorflow JS](https://www.tensorflow.org/js).

There are already many web APIs for accessing speech to text in the browser. They mostly center
around using an ASR provided by your system, or potentially making a WebRTC "phone call" to a server
which would stream back your conversation.

Some thoughts on using TFJS:
 - It was hard to get the featurizer to match up. I had to tweak the settings around the FFT many times
before it worked the same in TFJS and PyTorch.
 - Exporting PyTorch to TFJS required many steps
   - First a PyTorch model was exported to ONNX
   - Then, the ONNX got converted to tensorflow savedModel format using [onnx2tf](https://github.com/PINTO0309/onnx2tf)
   - Then the `tensorflowjs_converter` was used to convert that to TFJS format
 - Convolutional networks proved the easiest to export, which is why both the text and audio encoders are convolutional.
 - Performance is only "okay". There are many backends supported, including wasm, webgl, webgpu, and many hidden secret
 settings that affect performance.
   - The biggest perf killer was the fact that you need to call the joint network so often, and each time requires you
   to transfer memory around with the GPU. It feels like you could make a faster joint decoder in WASM directly, but then it is 
   not possible to swap backends midway through. And you do get a performance boost using the GPU for the big convolutions.

### Final Thoughts
There has been a lot of talk about multi-modal LLMs out there which can hold natural conversations, ex. 
[GPT-4o](https://openai.com/index/hello-gpt-4o/), or [Sindarin.tech](https://www.sindarin.tech/), or [Fixie.ai](https://fixie.ai/).

I wanted to present one currently impractical, weird, alternative way of doing speech recognition that could be a part
of a system like one of the above.

In the future, I want to cover some of the next steps that would need to be taken to make a great conversational AI.




