---
title: Pages
layout: page
permalink: /pages/
---

# Pages

{% assign items = site.pages | sort: 'date' | reverse %}
{% for item in site.pages %}
{% endfor %}

{%- comment -%}
  Die Collection heißt 'pages', daher greifst du mit site.pages darauf zu.
{%- endcomment -%}
{% assign items = site.pages | sort: 'date' | reverse %}
<ul>
{% for doc in items %}
  <li>
    <a href="{{ doc.url | relative_url }}">{{ doc.title | default: doc.name }}</a>
    {%- if doc.summary -%} – {{ doc.summary }}{%- endif -%}
  </li>
{% endfor %}
</ul>
