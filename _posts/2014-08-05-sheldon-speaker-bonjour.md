---
layout: post
title: Sheldon speaking, bonjour! - Leveraging Multilingual Tracks for (Weakly) Supervised Speaker Identification
author: Hervé Bredin
---

The **very first paper** experimenting with `TVD` has been accepted for oral presentation at **ACM MM'2014**.

### Abstract

We address the problem of **speaker identification in multimedia data**, and TV series in particular. While speaker identification is traditionally a supervised machine-learning task, our first contribution is to significantly **reduce the need for costly preliminary manual annotations** through the use of automatically aligned (and potentially noisy) fan-generated transcripts and subtitles. We show that both speech activity detection and speech turn identification modules trained in this weakly supervised manner achieve similar performance as their fully supervised counterparts (*i.e.* relying on fine manual speech/non-speech/speaker annotation). 

Our second contribution relates to **the use of multilingual audio tracks** usually available with this kind of content to significantly **improve the overall speaker identification performance**. Reproducible experiments (including dataset, manual annotations and source code) performed on the first six episodes of *The Big Bang Theory* TV series show that combining the French audio track (containing dubbed actor voices) with the English one (with the original actor voices) improves the overall English speaker identification performance by 5% absolute and up to 70% relative on the five main characters.

### Citation

```
@inproceedings{Bredin2014,
    Title = "Sheldon speaking, bonjour!" - Leveraging Multilingual Tracks for (Weakly) Supervised Speaker Identification,
    Author = Herv{\'e} Bredin and Anindya Roy and Nicolas P\^{e}cheux and Alexandre Allauzen,
    Booktitle = ACM Multimedia 2014, The 22nd ACM International Conference on Multimedia,
    Year = 2014,
    Location = Orlando, USA
}
```

### Reproducible research

The source code for this paper is available <a href="/research">here</a>.
