---
layout: post
title:  "Metric-Based Few-Short Learning for Video Action Recognition"
date:   2019-06-11 11:42:58 -0700
categories: research
description: In the few-shot scenario, a learner must effectively generalize to unseen classes given a small support set of labeled examples. While a relatively large amount of research has gone into few-shot learning for image classification, little work has been done on few-shot video classification.
img_path: /assets/dachshund_3.jpeg
img_text: wide-angle weenie
---
"Metric-based Few-shot Learning for Viewo Action Recognition" paper available on Arxiv. Read the full pdf [here][pdf-link].

`In the few-shot scenario, a learner must effectively generalize to unseen classes given a small support set of labeled examples. While a relatively large amount of research has gone into few-shot learning for image classification, little work has been done on few-shot video classification. In this work, we address the task of few-shot video action recognition with a set of two-stream models. We evaluate the performance of a set of convolutional and recurrent neural network video encoder architectures used in conjunction with three popular metric-based few-shot algorithms. We train and evaluate using a few-shot split of the Kinetics 600 dataset. Our experiments confirm the importance of the two-stream setup, and find prototypical networks and pooled long short-term memory network embeddings to give the best performance as few-shot method and video encoder, respectively. For a 5-shot 5-way task, this setup obtains 84.2% accuracy on the test set and 59.4% on a special “challenge” test set, composed of highly confusable classes.`

[pdf-link]: https://arxiv.org/pdf/1909.09602.pdf
