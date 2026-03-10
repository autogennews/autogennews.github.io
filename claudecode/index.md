---
layout: home
title: Claude Code News
permalink: /claudecode/
---

<h1 class="home-title">Claude Code News</h1>

{% assign claudecode_pages = site.pages | where_exp: "p", "p.url contains '/claudecode/'" | where_exp: "p", "p.url != '/claudecode/'" | sort: "date" | reverse %}

{% if claudecode_pages.size == 0 %}
<p style="color: #888;">No updates yet.</p>
{% else %}
<ul class="report-list">
{% for report in claudecode_pages %}
  <li>
    <a href="{{ report.url | relative_url }}">{{ report.title }}</a>
    {% if report.date %}<span class="date">{{ report.date | date: "%b %d, %Y" }}</span>{% endif %}
  </li>
{% endfor %}
</ul>
{% endif %}
