---
layout: splash
title: Connect to bioinformatics
permalink: /
author_profile: true    
header:
  overlay_color: "#0d9ea5"
  overlay_filter: "0.65"
  overlay_image:  /assets/img/photo_gallery/banner.jpg
  cta_label: 'Get connected'
  cta_url: "contact/"
  
excerpt: "RSG Belgium provides a network for bioinformaticians in Belgium."
---

## Our coverage

<div style="margin-top:10px;margin-top:10px;text-align:center">
    {% include institution-logo.html src="../assets/img/logo/institutions/kuleuven-greyscale.png" %}
    {% include institution-logo.html src="../assets/img/logo/institutions/uclouvain-greyscale.png" %}
    {% include institution-logo.html src="../assets/img/logo/institutions/uantwerp-greyscale.png" %}
    {% include institution-logo.html src="../assets/img/logo/institutions/uhasselt-greyscale.png" %}
    {% include institution-logo.html src="../assets/img/logo/institutions/ulb-greyscale.png" %}
    {% include institution-logo.html src="../assets/img/logo/institutions/uliege-greyscale.png" %}
    {% include institution-logo.html src="../assets/img/logo/institutions/vub-greyscale.png" %}
    {% include institution-logo.html src="../assets/img/logo/institutions/ughent-greyscale.svg" %}
</div>

## Our projects

<div style="margin-top:10px;margin-top:10px;text-align:center">
    <p><a href="{{site.url}}/about/"><img src="../assets/img/rsg_project.svg" style="max-height:250px;"></a></p>
</div>

## Supported by

<a href="https://www.iscbsc.org/"><img src="../assets/img/logo/ISCBSC-greyscale.png" style="max-width:240px;"></a>

## Latest posts

<div class="grid__wrapper">
  {% for post in site.posts limit:4 %}
    {% include archive-single.html type="grid"%}
  {% endfor %}
</div>

[Read more]({{site.url}}/news/)