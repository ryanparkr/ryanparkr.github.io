---
layout: page
permalink: /archive/
title: Post Archive
---

Most Recent Posts
{%for post in site.posts %} {% unless post.next %}
{% else %} {% capture month %}{{ post.date | date: '%B %Y' }}{% endcapture %} {% capture nmonth %}{{ post.next.date | date: '%B %Y' }}{% endcapture %} {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %} {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %} {% if year != nyear %}
{{ post.date | date: '%Y' }}
{% endif %} {% if month != nmonth %}
{{ post.date | date: '%B %Y' }}
{% endif %} {% endunless %}
{% if post.title and post.title != "" %}{{post.title}}{% else %}{{post.excerpt |strip_html}}{%endif%} - {% if post.date and post.date != "" %}{{ post.date | date: "%e %B %Y" }}{%endif%}

{% endfor %}
Oldest Posts
