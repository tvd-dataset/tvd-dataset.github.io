---
layout: default
title: Corpus
---

# {{ page.title }}

For obvious copyright reasons, the TVD corpus itself cannot be distributed.  
Instead, we provide all the necessary scripts to [reproduce](/reproduce) it locally.  
You just need to first legally acquired the corresponding TV series DVD sets.  

Once reproduced, here is what your local copy of TVD could look like:

```
tvd_root_directory/

   # one directory per TV series
   GameOfThrones/

      dvd/                                               the `dvd` directory contains multimedia 
                                                         content extracted from DVDs.

         dump/                                           the `dump` directory is where raw DVDs
            GameOfThrones.Season01.Disc01                are copied once and for all.                  
            GameOfThrones.Season01.Disc02
            ...

         rip/                                            the `rip` directory is where resources 
                                                         (video, audio and subtitles) are extracted 
                                                         from previously copied DVDs.
   
            video/
                                                         the `video` directory is where one video 
               GameOfThrones.Season01.Episode01.mkv      container is created for each available 
               GameOfThrones.Season01.Episode02.mkv      episode. `mkv` files contain high-resolution
               GameOfThrones.Season01.Episode03.mkv      video stream, multilingual audio stream and 
               GameOfThrones.Season01.Episode04.mkv      multilingual subtitles.
               ...

            audio/                                       the `audio` directory is where audio tracks 
                                                         are extracted for every available languages 
               GameOfThrones.Season01.Episode01.en.wav   in DVDs (in 16kHz wave files).
               GameOfThrones.Season01.Episode01.fr.wav
               GameOfThrones.Season01.Episode01.es.wav
               ...

            subtitles/                                   the `subtitles` directory is where subtitles
                                                         are extracted from DVDs for every available 
               GameOfThrones.Season01.Episode01.en.srt   languages (in .srt format).
               GameOfThrones.Season01.Episode01.fr.srt
               GameOfThrones.Season01.Episode01.es.srt
               ...
               
            stream/                                      the `stream` directory is where videos are 
                                                         optionally reencoded in webm, ogv and mp4 
               GameOfThrones.Season01.Episode01.webm     format for easy streaming.
               GameOfThrones.Season01.Episode01.ogv
               GameOfThrones.Season01.Episode01.mp4

      www/                                               the `www` directory contains metadata 
                                                         obtained from the Internet.

         resource_name_1/                                one directory per type of resources (e.g. 
                                                         manual_transcript or episode_summary).
            GameOfThrones.Season01.Episode01.json
            GameOfThrones.Season01.Episode02.json
            GameOfThrones.Season01.Episode03.json
            ...

         resource_name_2/

            GameOfThrones.Season01.Episode01.json
            GameOfThrones.Season01.Episode02.json
            GameOfThrones.Season01.Episode03.json
            ...

         imdb/                                           the `imdb` directory will eventually contain
                                                         metadata obtained from IMDB.com for every 
            GameOfThrones.Season01.Episode01.json        episode
            GameOfThrones.Season01.Episode02.json
            GameOfThrones.Season01.Episode03.json
            ...

         traktv/                                         the `traktv` directory will eventually 
                                                         contain metadata obtained from traktv.com 
            GameOfThrones.Season01.Episode01.json        for every episode
            GameOfThrones.Season01.Episode02.json
            GameOfThrones.Season01.Episode031.json
            ...            
```
