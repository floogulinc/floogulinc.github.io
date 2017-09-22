---
title: Contact
layout: default
permalink: /contact
order: 2
---

## Some of my accounts:

<ul>
{% assign filteredaccounts = site.data.accounts | where_exp: "account","account.name" %}
{% for account in filteredaccounts %}
<li>
{% if account.username %}{{ account.name }}: {% endif %}
{% if account.url %}<a href="{{account.url}}">{% endif %}
{% if account.username %}{{ account.username }}{% else %}
{{ account.name }}{% endif %}
{% if account.url %}</a>{% endif %}
{% if account.urls %}
<ul>
  {% for url in account.urls %}
  <li><a href="{{url.url}}">{{url.name}}</a></li>
  {% endfor %}
</ul>
{% endif %}
{% if account.accounts %}
<ul>
{% for subaccount in account.accounts %}
<li>
{% if subaccount.username %}{{ subaccount.name }}: {% endif %}
{% if subaccount.url %}<a href="{{subaccount.url}}">{% endif %}
{% if subaccount.username %}{{ subaccount.username }}{% else %}
{{ subaccount.name }}{% endif %}
{% if subaccount.url %}</a>{% endif %}
</li>
{% endfor %}
</ul>
{% endif %}
</li>
{% endfor %}
</ul>
