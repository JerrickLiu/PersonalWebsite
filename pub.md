---
title:
redirect_from:
  - /publications/
  - /publications.html
author_profile: true
---

<table>
{% for post in site.publications %}
  <tr>{% include _includes/publications.html %}</tr>
{% endfor %}
</table>