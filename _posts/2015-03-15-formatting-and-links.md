---
layout: post
title:  小狗第一次回村过年
date:   2025-02-22
tags: 龙傲天
categories: sample-posts
---

<div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4">
  {% for file in site.static_files %}
    {% if file.path contains '/assets/img/0222/' %}
      <div class="col">
        {% include figure.liquid path=file.path class="img-fluid rounded z-depth-1" zoomable=true %}
      </div>
    {% endif %}
  {% endfor %}
</div>
