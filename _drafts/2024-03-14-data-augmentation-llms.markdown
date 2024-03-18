---
layout: post
title:  "Data Augmentation for LLMs"
date:   2023-03-14 15:08:00 -0700
categories: research
---
Dataset augmentation is a common technique for improving the accuracy of machine learning models.
It is widely applied in domains such as vision[[1]](#1), and speech[[2]](#2), and traditional NLP[[3]](#3)[[4]](#4).

In this article, I want to show that there is ample evidence that this is being done to the big LLMs.

NB: Thank you to [Ahad Rana](https://github.com/ahadrana) for his help finding likely candidates for normalization.

We found that many of the best performing models (ChatGPT/Gemini/Claude) all have the ability to base64 decode text,
parse the International Phonetic Alphabet, and deal with less clean input prompts (typing mistakes, etc).

The theory is that one of the undocumented training "tricks" being used is a low percentage of dataset augmentation
where some words/sentences/phrases in the pre-training corpus are being replaced with their base64/IPA/thesaurus
equivalents.

The literature cited above shows that it's pretty clear that dataset augmentation does improve performance
across the board. Even simple augmentations like randomly deleting characters, simulating typing mistakes, etc.
give improvements on NLP tasks. And more advanced ones like replacing words with synonyms help even more[[4]](#4).

And yet, most of the big papers describing training open LLMs like Llama[[6]](#6)/Olmo[[7]](#7) don't mention training data
augmentations.

As companies move beyond training just a single epoch through their training datasets, augmentation will
play an even bigger part of preventing overfitting.

### Base64 Decoding
It's been known since at least Dec 2022 that ChatGPT could encode/decode base64 text. [[5]](#5)

However, it can also hold entire conversations in base64.

### International Phonetic Alphabet (IPA)


### References 
<a id="1">[1]</a>
Shorten, Connor, and Taghi M. Khoshgoftaar. "A Survey on Image Data Augmentation for Deep Learning." Journal of Big Data, vol. 6, no. 1, 2019. <a href="https://jbigdata.springeropen.com/articles/10.1186/s40537-019-0197-0">https://jbigdata.springeropen.com/articles/10.1186/s40537-019-0197-0</a>

<a id="2">[2]</a>
Park, Daniel S., et al. "SpecAugment: A Simple Data Augmentation Method for Automatic Speech Recognition." 2019. <a href="https://arxiv.org/abs/1904.08779">https://arxiv.org/abs/1904.08779</a>

<a id="3">[3]</a> Wei, Jason, and Kai Zou. "EDA: Easy Data Augmentation Techniques for Boosting Performance on Text Classification Tasks." EMNLP-IJCNLP 2019. <a href="https://arxiv.org/abs/1901.11196">https://arxiv.org/abs/1901.11196</a>

<a id="4">[4]</a> Dai, Haixing; Liu, Zhengliang; Liao, Wenxiong, et al. "AugGPT: Leveraging ChatGPT for Text Data Augmentation." 2023. arXiv preprint arXiv:2302.13007. <a href="https://doi.org/10.48550/arxiv.2302.13007">https://doi.org/10.48550/arxiv.2302.13007</a>

<a id="5">[5]</a> Reddit Post https://www.reddit.com/r/ChatGPT/comments/zd9fjp/chatgpt_knows_how_to_decode_base64/

<a id="6">[6]</a> "Llama 2: Open Foundation and Fine-Tuned Chat Models." arXiv preprint arXiv:2307.09288. <a href="https://arxiv.org/abs/2307.09288">https://arxiv.org/abs/2307.09288</a>

<a id="7">[7]</a> Groeneveld, Dirk, et al. "OLMo: Accelerating the Science of Language Models." 2023. <a href="https://ar5iv.org/abs/2402.00838">https://ar5iv.org/abs/2402.00838</a>
