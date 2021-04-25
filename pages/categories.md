---
layout: default
title:  "カテゴリー別記事一覧"
description: "あーるのシレン2 TA日記のカテゴリー別の記事一覧ページです"
keyword: "挨拶,配信"
date:   2021-04-23 12:00:00
permalink: /categories
---

{% for category in site.categories %}
{% capture name %}{{ category[0] }}{% endcapture %}
<h2>{{ name }} ({{ site.categories[name] | size }})</h2>
<ul class="posts">
{% for post in site.categories[name] %}
<li>
    <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
    <span class="post-date">{{ post.date | date_to_string }}</span>
</li>
{% endfor %}
</ul>
{% endfor %}