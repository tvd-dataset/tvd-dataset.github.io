---
layout: default
title: Reproducing TVD
---

# {{ page.title }}

## Pre-requisite

`TVD.create` scripts are mostly wrappers around open-source command line tools -- which may be cumbersome to install.  
Therefore, we provide a [Docker](http://www.docker.io) image with every dependency pre-installed (vobcopy, lsdvd, HandBrakeCLI, mencoder, vobsub2srt, avconv, sndfile-resample and tesseract).

```bash
$ export TVD_SCRIPT=/path/to/tvd_script
$ git clone http://www.github.com/tvd-dataset/tvd $TVD_SCRIPT
$ cd $TVD_SCRIPT && docker build -t tvd .
```

If you prefer not to use Docker, you can still have a look at the [Dockerfile](https://github.com/tvd-dataset/tvd/blob/master/Dockerfile) for details on how to install all dependencies for Ubuntu 12.04 LTS.

## Reproduction

The following steps show how to generate the `GameOfThrones` `TVD` subset.  
Each subset is actually described by a [TVD series plugin](/plugins).  
You are encouraged to [contribute with your own](https://github.com/tvd-dataset/tvd-plugin).

### Decide where to store your copy of the TVD corpus

```bash
$ export TVD_CORPUS='/path/to/tvd_corpus'
```

### Select `TVD` subset

```bash
$ export TVD_PLUGIN='GameOfThrones'
```

### Dump `GameOfThrones` DVDs

This is achieved using `dump` mode of `tvd.create` module.

```bash
# insert first DVD of first season
$ export SEASON=1
$ export DISC=1
```
#### With Docker

```bash
$ docker run -v $TVD_CORPUS:/tvd -v /path/to/dvd:/dvd tvd python -m tvd.create dump --dvd /dvd /tvd $TVD_PLUGIN $SEASON $DISC
```
#### Without Docker

```bash
$ python -m tvd.create dump --help
```

Repeat for second DVD (DISC=2), third DVD, (you got the idea...)

### Extract multilingual video, audio and subtitles

This is achieved using `rip` mode of `tvd.create` module.

```bash
$ export SEASON=1
```

#### With Docker

```bash
$ docker run -v $TVD_CORPUS:/tvd python -m tvd.create rip --tessdata /tessdata /tvd $TVD_PLUGIN $SEASON
```

#### Without Docker

```bash
$ python -m tvd.create rip --help
```

### Download metadata from the Internet

This is achieved using `www` mode of `tvd.create` module.

#### With Docker

```bash
$ docker run -v $TVD_CORPUS:/tvd python -m tvd.create www /tvd $TVD_PLUGIN
```

#### Without Docker

```bash
$ python -m tvd.create www --help
```

### (Optionally) re-encode videos for later streaming

This is achieved using `stream` mode of `tvd.create` module.

#### With Docker

```bash
$ docker run -v $TVD_CORPUS:/tvd python -m tvd.create stream /tvd $TVD_PLUGIN
```

#### Without Docker

```bash
$ python -m tvd.create stream --help
```
