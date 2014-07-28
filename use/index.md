---
layout: default
title: Using TVD
---

# {{ page.title }}


```bash
$ pip install TVDGameOfThrones
```

```python
>>> from tvd import GameOfThrones
>>> gameOfThrones = GameOfThrones('/path/to/tvd_corpus')
>>> firstEpisode = gameOfThrones.episodes[0]
>>> print firstEpisode
>>> GameOfThrones.Season01.Episode01
>>> scenes = gameOfThrones.get_resource('scenes', episode)
>>> for segment, _, scene in scenes.itertracks(label=True)
...     print segment, scene
```
