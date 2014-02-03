---
layout: bootstrap
title: People
---

## Contributors

{% for contributor in site.data.contributors %}
 * [{{ contributor.name }}]({{ contributor.web }})
{% endfor %}
