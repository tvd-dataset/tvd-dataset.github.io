---
layout: post
title: Structured Prediction for Speaker Identification in TV Series
author: Hervé Bredin
---

Our [/assets/pdf/Knyazeva2015.pdf](second paper) experimenting with `TVD` has been accepted to **InterSpeech'2015**.

### Abstract

Though radio and TV broadcast are **highly structured documents**, state-of-the-art speaker identification algorithms do not take advantage of this information to improve prediction performance: speech turns are usually identified independently from each other, using unstructured multi-class classification approaches. In this work, we propose to **address speaker identification as a sequence labeling task** and use two structured prediction techniques to **account for the inherent temporal structure of interactions between speakers**: the first one relies on Conditional Random Field and can take into account local relations between two consecutive speech turns; the second one, based on the SEARN framework, sacrifices exact inference for the sake of the expressiveness of the model and is able to incorporate rich structure information during prediction. Experiments performed on The Big Bang Theory TV series show that structured prediction techniques outperform the standard unstructured approach.

### Citation

```
@inproceedings{Knyazeva2015,
		Title = {{Structured Prediction for Speaker Identification in TV Series}},
		Author = {Elena Knyazeva and Guillaume Wisniewski and Herv\'{e} Bredin and Fran\c{c}ois Yvon},
		Booktitle = {Interspeech 2015, 16th Annual Conference of the International Speech Communication Association},
		Year = {2015},
		Month = {September},
		Address = {Dresden, Germany},
		}
```
