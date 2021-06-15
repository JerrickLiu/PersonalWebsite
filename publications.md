---
title: Publications
subtitle: Here's what I've done so far
---

<table>
{% for post in site.publications reversed %}
  <tr>{% include publication.html %}</tr>
{% endfor %}
</table>