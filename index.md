---
layout: default
permalink: /
---

<img src="avatar.png" style="display: block; margin: auto;"> 

# Welcome

I'm Paul Friederichsen and this is my site. It's a work in progress.

## Contact Info:

<ul>
{% assign filteredaccounts = site.data.accounts | where_exp: "account","account.tags contains 'main'" %}
{% for account in filteredaccounts %}
<li>
{% if account.username %}{{ account.name }}: {% endif %}{% if account.url %}<a href="{{account.url}}">{% endif %}{% if account.username %}{{ account.username }}{% else %}{{ account.name }}{% endif %}{% if account.url %}</a>{% endif %}
</li>
{% endfor %}
</ul>
