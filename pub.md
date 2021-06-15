---
title:
redirect_from:
  - /publications/
  - /publications.html
author_profile: true
---

<table>
{% for post in site.publications %}
  <tr>{% include publications.html %}</tr>
{% endfor %}
</table>