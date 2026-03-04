---
layout: post
title:  小狗第一次回村过年
date:   2025-02-22
tags: 龙傲天
categories: sample-posts
---

<div class="row">
    {% for file in site.static_files %}
        {% if file.path contains 'assets/img/0222' %}
            <div class="col-sm mt-3 mt-md-0">
                {% include figure.liquid path=file.path class="img-fluid rounded z-depth-1" zoomable=true %}
            </div>
        {% endif %}
    {% endfor %}
</div>
