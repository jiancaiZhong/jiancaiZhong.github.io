---
layout: mypost
title: 网页导航
---

以下是我收藏的网页，可以当作我的书签。


<ul>
  {%- for link in site.links %}
  <li>
    <p><a href="{{ link.url }}" title="{{ link.desc }}" target="_blank" >{{ link.title }}</a></p>
  </li>
  {%- endfor %}
</ul>
