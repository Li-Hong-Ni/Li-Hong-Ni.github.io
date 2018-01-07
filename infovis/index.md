---
layout: archive
title: "信息可视化作品集"
date: 2018-1-1T14:25:45-04:00
modified:
excerpt: "加油"
tags: []
image: 
  feature: 
  teaser:
---

- <a href="https://public.tableau.com/profile/minra#!/vizhome/children_0/1?publish=yes" target="_blank">![数据分析.png](https://i.loli.net/2018/01/07/5a51dae1bd0a2.png)</a>

其他作品
<div class="tiles">
{% for post in site.categories.visualization %}
  {% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles 把所有categories 有 visualization 的列出来-->