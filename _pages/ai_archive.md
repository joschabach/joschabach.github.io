---
layout: archive
author_profile: false
permalink: ai/index.html
---

{% include base_path %}

<h3 class="archive__subtitle">AI and Cognition</h3>

{% for post in paginator.posts %}
  {{ post.category }}
  {% if post.category == "AI and Cognition" %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}

{% include paginator.html %}