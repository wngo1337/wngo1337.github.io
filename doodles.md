---
layout: page
title: Doodles
---
Some people picked up baking during the pandemic. I picked up doodling. I think Snoopy is fun. I'm getting better (_I hope!!_) at drawing him every day.

{% for image in site.static_files %}
{% if image.path contains 'img/snoopy' %}
![JonasBrothers]({{ "{{ image.path }}" | relative_url }})
{% endif %}
{% endfor %}




