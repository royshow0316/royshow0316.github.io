---
layout: default
title: 類別
permalink: /categories/
---

<h2>類別</h2>

<div>
  {% for cat in site.categories %}
  <a class="linknoline" href="#{{ cat[0] }}" title="{{ cat[0] }}" rel="{{ cat[1].size }}">
    {{ cat[0] }} <span style="color:#07e"> ({{ cat[1].size }})</span>
  </a>&nbsp;&nbsp;&nbsp;
  {% endfor %}
</div>

<hr class="page_hr">

<ul class="listing">
  {% for cat in site.categories %}
    <li class="listing-seperator" id="{{ cat[0] }}">{{ cat[0] }}</li>
    <p class="listing-item">
      {% for post in cat[1] %}
        {% if post.archive != true %}
        <time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time>
        &nbsp;&nbsp;&nbsp;
        <a href="{{ post.url }}" target='blank' title="{{ post.title }}">{{ post.title }}</a>
        <br/>
        {% endif %}
      {% endfor %}
    </p>
  {% endfor %}
</ul>