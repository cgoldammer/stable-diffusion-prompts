---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---



{% for dt in site.data %}
{% assign topicData = dt[1] %}
{% assign topic = dt[0] %}
# {{ topicData.name }}

## How to create
- prompt: {{ topicData.prompt }}
- cfg Scale: {{ topicData.cfg_scale }}
- Sampler: {{ topicData.sampler }}
- steps: {{ topicData.steps }}

{% for img in topicData.images %}

## Images
### {{ img.name }}
![{{img.name}}](/assets/img/{{ img.file }}){:class="img-responsive"}
Attribution: {{ img.attribution }}
{% endfor %}

{% endfor %}
