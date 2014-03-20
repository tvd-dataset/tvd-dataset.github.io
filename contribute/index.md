---
layout: default
title: Contributing to TVD
---

# {{ page.title }}

## List of contributors

{% for contributor in site.data.contributors %}
  - [{{ contributor.name }}]({{ contributor.web }}) -- {{ contributor.contribution }}
{% endfor %}

## How can I contribute?

Here are a few examples how you can contribute to `TVD`

  - [create a plugin](http://www.github.com/tvd-dataset/tvd-plugin) for a new TV series
  - update [existing plugin](/plugins) (using GitHub [pull requests]() workflow)
  - improve `tvd.create` reproduction script (using GitHub [pull requests]() workflow)
  - write a blog post describing how `TVD` is useful for your research

