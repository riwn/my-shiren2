---
layout: default
title:  "タグ別記事一覧"
description: "あーるのシレン2 TA日記のタグ別の記事一覧ページです"
date:   2021-04-23 12:00:00
permalink: /tags
---

{% for tag in site.tags %}
  {% capture name %}{{ tag[0] }}{% endcapture %}
  <h2>{{ name }} ({{ site.tags[name] | size }})</h2>
  <ul class="posts" style="list-style: none;">
  {% for post in site.tags[name] %}
    <li>
        <div class="card mb-3" style="max-width: 540px;">
            <div class="row no-gutters">
                <div class="col-md-8">
                    <div class="card-body">
                    <a href="{{ post.url | prepend: site.baseurl }}">
                        <h6 class="card-title">{{ post.title }}</h6>
                    </a>
                    <p class="card-text"><small class="text-muted"><span>{{ post.date | date_to_string }}</span></small></p>
                    </div>
                </div>
            </div>
      </div>
    </li>
  {% endfor %}
  </ul>
{% endfor %}