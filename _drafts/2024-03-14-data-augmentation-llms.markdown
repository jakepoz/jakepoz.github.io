---
layout: post
title:  "Data Augmentation for LLMs"
date:   2023-03-14 15:08:00 -0700
categories: research
---
Dataset augmentation is a common technique for improving the accuracy of machine learning models.
It is widely applied in domains such as vision[[1]](#1), and speech[[2]](#2), and traditional NLP[[3]](#3).

In this article, I want to show that there is ample evidence that this is being done to the big LLMs.

NB. Thank you to [Ahad Rana](https://github.com/ahadrana) for his help finding likely candidates for normalization.



### References 
<a id="1">[1]</a>
Shorten, Connor, and Taghi M. Khoshgoftaar. "A Survey on Image Data Augmentation for Deep Learning." Journal of Big Data, vol. 6, no. 1, 2019. <a href="https://jbigdata.springeropen.com/articles/10.1186/s40537-019-0197-0">https://jbigdata.springeropen.com/articles/10.1186/s40537-019-0197-0</a>

<a id="2">[2]</a>
Park, Daniel S., et al. "SpecAugment: A Simple Data Augmentation Method for Automatic Speech Recognition." 2019. <a href="https://arxiv.org/abs/1904.08779">https://arxiv.org/abs/1904.08779</a>

<a id="3">[3]</a> Wei, Jason, and Kai Zou. "EDA: Easy Data Augmentation Techniques for Boosting Performance on Text Classification Tasks." EMNLP-IJCNLP 2019. <a href="https://arxiv.org/abs/1901.11196">https://arxiv.org/abs/1901.11196</a>