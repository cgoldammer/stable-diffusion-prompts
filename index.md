---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

This is a companion site to [publicprompts.art](https://publicprompts.art/). 
Our goal is to share good prompts as open source. By design, all prompts in here are available 
as raw data in the `_data` folder. We encourage participation and will gladly merge PRs if 
they fit in the existing structure.

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
