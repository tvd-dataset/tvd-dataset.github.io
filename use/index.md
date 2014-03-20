---
layout: default
title: Using TVD
---

# {{ page.title }}


`TVD` scripts are written in Python and can be installed using `pip`:

```bash
$ pip install tvd
```

`TVD` series plugins can be installed similarly:

```bash
$ pip install TVDGameOfThrones
$ pip install TVDTheBigBangTheory
```

```python
>>> from tvd import Episode
>>> from tvd.series import GameOfThrones
>>> gameOfThrones = GameOfThrones(tvd='/path/to/tvd')
>>> SERIES = "GameOfThrones"
>>> episode = Episode(series=SERIES, season=1, episode=1)
>>> gameOfThrones.path_to_audio(episode, language='fr')
```
