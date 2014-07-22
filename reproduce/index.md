---
layout: default
title: Reproducing TVD
---

# {{ page.title }}

#### Step 0 | Get DVDs

For obvious copyright reasons, TV series episodes cannot be freely distributed. Instead, we provide scripts to reproduce the corpus locally from your own legal copy of the official DVD sets.

#### Step 1 | Download scripts

Reproduction scripts are mostly wrappers around open-source command line tools which may be cumbersome to install. Therefore, we encourage you to use the provided [Docker](http://www.docker.io) image that comes with all dependencies pre-installed. *If you would rather not use Docker, have a look at the [Dockerfile](https://github.com/tvd-dataset/tvd/blob/master/Dockerfile) for details on how to install all dependencies for Ubuntu 12.04 LTS.*

```bash
$ export TVD_SCRIPT=/path/to/tvd_script
$ git clone http://www.github.com/tvd-dataset/tvd $TVD_SCRIPT
$ cd $TVD_SCRIPT && docker build -t tvd .
```

The following steps (2 and 3) suppose that you are trying to reproduce `GameOfThrones` [subset](/plugins): 

```bash
$ export TVD_CORPUS='/path/to/tvd_corpus'
$ export TVD_PLUGIN='GameOfThrones'
```

#### Step 2 | Get audio, video and subtitles

`tvd.create dump` copies DVDs on your hard drive once and for all.

```bash
$ export SEASON=1; export DISC=1;
$ docker run -v $TVD_CORPUS:/tvd -v /path/to/dvd:/dvd tvd \
  python -m tvd.create dump --dvd /dvd /tvd $TVD_PLUGIN $SEASON $DISC
```

`tvd.create rip` extracts audio, video and subtitles.

```bash
$ export SEASON=1
$ docker run -v $TVD_CORPUS:/tvd tvd \
  python -m tvd.create rip --tessdata /tessdata /tvd $TVD_PLUGIN $SEASON
```

#### Step 3 | Get metadata

`tvd.create metadata` copies metadata provided by the plugin.

```bash
$ python -m tvd.create metadata $TVD_CORPUS $TVD_PLUGIN
```


#### Step 4 | Tadaaaaa!

```
/path/to/tvd_corpus/GameOfThrones
├── dvd
│   ├── dump
│   │   ├── GameOfThrones.Season01.Disc01
│   │   ├── GameOfThrones.Season01.Disc02
│   │   └── ...
│   └── rip
│       ├── video
│       │   ├── GameOfThrones.Season01.Episode01.mkv
│       │   ├── GameOfThrones.Season01.Episode02.mkv
│       │   ├── GameOfThrones.Season01.Episode03.mkv
│       │   ├── GameOfThrones.Season01.Episode04.mkv
│       │   └── ...
│       ├── audio
│       │   ├── GameOfThrones.Season01.Episode01.en.wav
│       │   ├── GameOfThrones.Season01.Episode02.fr.wav
│       │   └── ...
│       └── subtitles
│           ├── GameOfThrones.Season01.Episode01.en.srt
│           ├── GameOfThrones.Season01.Episode02.fr.srt
│           └── ...
└── metadata
    ├── transcript
    │   ├── GameOfThrones.Season01.Episode01.json
    │   ├── GameOfThrones.Season01.Episode02.json
    │   └── ...
    ├── scenes
    │   ├── GameOfThrones.Season01.Episode01.json
    │   ├── GameOfThrones.Season01.Episode02.json
    │   └── ...
    └── ...
```

Why don't you try and [have fun](/use) with `TVD`?