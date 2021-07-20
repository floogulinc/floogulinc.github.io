---
title: Home
layout: default
permalink: /
order: 1
---

# Welcome

I'm Paul Friederichsen and this is my site. It's a work in progress.

## Contact Info:

{% assign filteredaccounts = site.data.accounts | where_exp: "account","account.tags contains 'main'" %}
{% include listaccounts.html tag="main" %}
