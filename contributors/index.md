---
layout: page
title: "Contributors"
date: 2015-09-22 -0800
comments: false
categories: [project blog]
sharing: false
---

## Contributors

<ul>
{% for contributor in site.github.contributors %}
  <li>
    <img src="{{ contributor.avatar_url }}" width="32" height="32" /> <a href="{{ contributor.html_url }}">{{ contributor.login }}</a>
  </li>
{% endfor %}
</ul>
