---
layout: archive
title: News
permalink: /news/
author_profile: true
defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      read_time: false
      comments: true
      share: true
      related: true
---

<div>
    <div style="float:left;width:70%;padding-right:5%">
        {% capture written_year %}'None'{% endcapture %}
        {% for post in site.posts %}
             {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
             {% if year != written_year %}
                  {% capture written_year %}{{ year }}{% endcapture %}
             {% endif %}
             {% include archive-single.html %}
         {% endfor %}
    </div> 
    <div style=" float:right;width:30%;">
        {% twitter https://twitter.com/RSGBelgium maxwidth=300 limit=3 %}
    </div>
</div>

<div style="clear:both"/>

