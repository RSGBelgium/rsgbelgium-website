---
layout: splash
permalink: /
author_profile: true
header:
  #overlay_color: "#378973"
  overlay_color: "#0d9ea5"
  overlay_filter: "0.5"
  overlay_image: /assets/img/RSGlogoBelgium-banner.png
  cta_label: "Subscribe to our mailing list"
  cta_url: "http://listserver.ua.ac.be/sympa/subscribe/rsg-belgium"
  # caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
excerpt: "RSG Belgium provides a network for young computational biology and bioinformatics students and researchers in Belgium."
# <br/><br/>To stay informed about our activities, head over to our events page, social media accounts or mailing list."
intro:
  - excerpt: 'Welcome to the homepage of **RSG Belgium**, the Belgian branch of the **ISCB Student Council Regional Groups**.<br>If you are interested in joining our network or if you just want to keep up to date on the latest RSG Belgium news, please check out our [upcoming activities](/events/), follow our social media accounts (<i class="fa fa-twitter" aria-hidden="true"></i> [Twitter](https://twitter.com/rsgbelgium) & <i class="fa fa-facebook" aria-hidden="true"></i> [Facebook](https://www.facebook.com/RSGBelgium)), join our <i class="fa fa-slack" aria-hidden="true"></i> [Slack channel](mailto:rsg-belgium@iscbsc.org?Subject=RSG%20Slack%20Subscription&Body=I%20would%20like%20to%20join%20the%20RSG%20Belgium%20Slack%20channel%2E) or subscribe to the <i class="fa fa-envelope-o" aria-hidden="true"></i> [mailing list](http://listserver.ua.ac.be/sympa/subscribe/rsg-belgium).<br>We hope to see you at one of our upcoming events!'
feature_row:
  - #image_path: assets/images/unsplash-gallery-image-1-th.jpg
    #alt: "placeholder image 1"
    title: "Events"
    excerpt: "An overview of our upcoming<br>and previous activities.<br>"
    url: "/events/"
    btn_label: "Activities overview"
    btn_class: "btn--primary"
  - #image_path: /assets/images/unsplash-gallery-image-3-th.jpg
    title: "Organization"
    excerpt: "The people behind **RSG Belgium**.<br><br>"
    url: "/organization/"
    btn_label: "Meet the team"
    btn_class: "btn--primary"
  - #image_path: /assets/images/unsplash-gallery-image-2-th.jpg
    #alt: "placeholder image 2"
    title: "Mission statement"
    excerpt: "The goals and ambitions of **RSG Belgium**.<br><br>"
    url: "/mission/"
    btn_label: "Read more"
    btn_class: "btn--primary"
feature_row_posts:
    title: "Recent posts"    
---


<!-- #feature_row2:
#  - image_path: /assets/images/unsplash-gallery-image-2-th.jpg
#    alt: "placeholder image 2"
#    title: "Placeholder Image Left Aligned"
#    excerpt: 'This is some sample content that goes here with **Markdown** formatting. Left aligned with `type="left"`'
#    url: "#test-link"
#    btn_label: "Read More"
#    btn_class: "btn--primary"
#feature_row3:
#  - image_path: /assets/images/unsplash-gallery-image-2-th.jpg
#    alt: "placeholder image 2"
#    title: "Placeholder Image Right Aligned"
#    excerpt: 'This is some sample content that goes here with **Markdown** formatting. Right aligned with `type="right"`'
#    url: "#test-link"
#    btn_label: "Read More"
#    btn_class: "btn--primary"
#feature_row4:
#  - image_path: /assets/images/unsplash-gallery-image-2-th.jpg
#    alt: "placeholder image 2"
#    title: "Placeholder Image Center Aligned"
#    excerpt: 'This is some sample content that goes here with **Markdown** formatting. Centered with `type="center"`'
#    url: "#test-link"
#    btn_label: "Read More"
#    btn_class: "btn--primary" -->

<!-- {% include figure image_path="/assets/img/RSGlogoBelgium.png" alt="this is a placeholder image" caption="This is a figure caption." %} -->


{% include feature_row id="intro" type="center" %}


{% include feature_row %}


# Recent posts

<div class="grid__wrapper">
  {% for post in site.posts limit:3 %}
    {% include archive-single.html type="grid" %}
  {% endfor %}
</div>










<!-- {% include feature_row_posts %} -->

<!-- <div class="grid__wrapper">
  {% for post in site.portfolio %}
    {% include archive-single.html type="grid" %}
  {% endfor %}
</div>




{% for f in site.posts limit:3 %}

{% if f.url contains "://" %}
  {% capture f_url %}{{ f.url }}{% endcapture %}
{% else %}
  {% capture f_url %}{{ f.url | absolute_url }}{% endcapture %}
{% endif %}

<div class="feature__item{% if include.type %}--{{ include.type }}{% endif %}">
  <div class="archive__item">
    {% if f.image_path %}
      <div class="archive__item-teaser">
        <img src=
          {% if f.image_path contains "://" %}
            "{{ f.image_path }}"
          {% else %}
            "{{ f.image_path | absolute_url }}"
          {% endif %}
        alt="{% if f.alt %}{{ f.alt }}{% endif %}">
      </div>
    {% endif %}

    <div class="archive__item-body">
      {% if f.title %}
        <h2 class="archive__item-title">{{ f.title }}</h2>
      {% endif %}

      {% if f.excerpt %}
        <div class="archive__item-excerpt">
          {{ f.excerpt | markdownify }}
        </div>
      {% endif %}

      {% if f.url %}
        <p><a href="{{ f_url }}" class="btn {{ f.btn_class }}">{{ f.btn_label | default: site.data.ui-text[site.locale].more_label | default: "Learn More" }}</a></p>
      {% endif %}
    </div>
  </div>
</div>

{% endfor %} -->












<!-- {% capture written_year %}'None'{% endcapture %}
{% for post in site.posts %}
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
  {% if year != written_year %}
    {% capture written_year %}{{ year }}{% endcapture %}
  {% endif %}
  {% include archive-single.html %}
{% endfor %} -->










<!-- {% include feature_row id="feature_row2" type="left" %}

{% include feature_row id="feature_row3" type="right" %}

{% include feature_row id="feature_row4" type="center" %} -->
