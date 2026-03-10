---
layout: page
title: Agentic AI News
permalink: /ainews/
---

{% assign ainews_pages = site.pages | where_exp: "p", "p.url contains '/ainews/'" | where_exp: "p", "p.url != '/ainews/'" | sort: "date" | reverse %}

{% if ainews_pages.size == 0 %}
<p style="color: #888;">No reports yet.</p>
{% else %}
<ul class="report-list">
{% for report in ainews_pages %}
  <li>
    <a href="{{ report.url | relative_url }}">{{ report.title }}</a>
    {% if report.date %}<span class="date">{{ report.date | date: "%b %d, %Y" }}</span>{% endif %}
  </li>
{% endfor %}
</ul>
{% endif %}
