---
layout: page
title: AI News Reports
permalink: /ainews/
---

Weekly AI agent intelligence briefings.

## Reports

{% assign ainews_pages = site.pages | where_exp: "p", "p.url contains '/ainews/'" | where_exp: "p", "p.url != '/ainews/'" | sort: "date" | reverse %}

{% if ainews_pages.size == 0 %}
No reports found.
{% else %}
<ul>
{% for report in ainews_pages %}
  <li>
    <a href="{{ report.url | relative_url }}">{{ report.title }}</a>
    {% if report.date %}<span style="color: #666; margin-left: 0.5em;">&mdash; {{ report.date | date: "%B %d, %Y" }}</span>{% endif %}
  </li>
{% endfor %}
</ul>
{% endif %}
