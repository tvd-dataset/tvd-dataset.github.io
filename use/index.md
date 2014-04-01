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
>>> episode = Episode(series="GameOfThrones", season=1, episode=1)
>>> from tvd import GameOfThrones, AnnotationGraph
>>> gameOfThrones = GameOfThrones('/path/to/tvd/directory/')
>>> outline =  AnnotationGraph.load(gameOfThrones.path_to_resources(episode, 'outline')
```
