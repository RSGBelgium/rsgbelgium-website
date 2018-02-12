---
layout: splash
permalink: /
author_profile: true
header:
  #overlay_color: "#378973"
  overlay_color: "#0d9ea5"
  overlay_filter: "0.4"
  overlay_image: /assets/img/RSGlogoBelgium-banner-notext.png
  cta_label: "Subscribe to our mailing list"
  cta_url: "http://listserver.ua.ac.be/sympa/subscribe/rsg-belgium"
  # caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
excerpt: "RSG Belgium provides a network for young computational biology and bioinformatics students and researchers in Belgium."
# <br/><br/>To stay informed about our activities, head over to our events page, social media accounts or mailing list."
intro:
  - excerpt: 'Welcome to the homepage of **RSG Belgium**, the Belgian branch of the <br>**ISCB Student Council''s Regional Student Groups**.<br><br>If you are interested in joining our network or if you just want to stay up to date on the latest RSG Belgium news, please check out our <br>announcements and upcoming activities in the [news section <i class="far fa-newspaper" aria-hidden="true"></i>](/news/), <br>follow our social media accounts [Twitter <i class="fab fa-twitter" aria-hidden="true"></i>](https://twitter.com/rsgbelgium){:target="_blank"} & [Facebook <i class="fab fa-facebook" aria-hidden="true"></i>](https://www.facebook.com/RSGBelgium){:target="_blank"}, <br>come and have a chat on our [Slack channel <i class="fab fa-slack" aria-hidden="true"></i>](/slack/) <br>or subscribe to the [mailing list <i class="fas fa-envelope-open" aria-hidden="true"></i>](http://listserver.ua.ac.be/sympa/subscribe/rsg-belgium).<br><br>We hope to see you at one of our upcoming events!'
#[Slack channel <i class="fab fa-slack" aria-hidden="true"></i>](mailto:rsg-belgium@iscbsc.org?Subject=RSG%20Slack%20Subscription&Body=I%20would%20like%20to%20join%20the%20RSG%20Belgium%20Slack%20channel%2E
feature_row:
  - #image_path: assets/images/unsplash-gallery-image-1-th.jpg
    #alt: "placeholder image 1"
    title: "News"
    # excerpt: "An overview of our upcoming<br>and previous activities, as well as <br>general announcements."
    excerpt: "General announcements and an overview of past and future events."
    url: "/news/"
    btn_label: "News and activities"
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

{% include feature_row id="intro" type="center" %}

{% include feature_row %}

# Recent announcements

<div class="grid__wrapper">
  {% for post in site.posts limit:3 %}
    {% include archive-single.html type="grid" %}
  {% endfor %}
</div>
