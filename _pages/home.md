---
layout: splash
permalink: /
author_profile: true
header:
  overlay_color: "#378973"
  overlay_filter: "0.8"
  #overlay_image: /assets/images/unsplash-image-1.jpg
  cta_label: "Subscribe to mailing list"
  cta_url: "https://lists.ugent.be/sympa/subscribe/rsg_belgium"
  #caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
excerpt: "RSG Belgium provides a network for young bioinformaticians and computational biology students and researchers in Belgium. <br/><br/>To stay informed about our activites, check out our social media pages and mailing list."
intro:
  - excerpt: 'Short description.'
feature_row:
  - #image_path: assets/images/unsplash-gallery-image-1-th.jpg
    #alt: "placeholder image 1"
    title: "Events"
    excerpt: "An overview of our upcoming and previous activities."
    url: "/events/"
    btn_label: "Activities overview"
    btn_class: "btn--primary"
  - #image_path: /assets/images/unsplash-gallery-image-2-th.jpg
    #alt: "placeholder image 2"
    title: "Mission statement"
    excerpt: "The goals and ambitions of **RSG Belgium**."
    url: "/mission/"
    btn_label: "Read more"
    btn_class: "btn--primary"
  - image_path: /assets/images/unsplash-gallery-image-3-th.jpg
    title: "Placeholder 3"
    excerpt: "This is some sample content that goes here with **Markdown** formatting."
feature_row2:
  - image_path: /assets/images/unsplash-gallery-image-2-th.jpg
    alt: "placeholder image 2"
    title: "Placeholder Image Left Aligned"
    excerpt: 'This is some sample content that goes here with **Markdown** formatting. Left aligned with `type="left"`'
    url: "#test-link"
    btn_label: "Read More"
    btn_class: "btn--primary"
feature_row3:
  - image_path: /assets/images/unsplash-gallery-image-2-th.jpg
    alt: "placeholder image 2"
    title: "Placeholder Image Right Aligned"
    excerpt: 'This is some sample content that goes here with **Markdown** formatting. Right aligned with `type="right"`'
    url: "#test-link"
    btn_label: "Read More"
    btn_class: "btn--primary"
feature_row4:
  - image_path: /assets/images/unsplash-gallery-image-2-th.jpg
    alt: "placeholder image 2"
    title: "Placeholder Image Center Aligned"
    excerpt: 'This is some sample content that goes here with **Markdown** formatting. Centered with `type="center"`'
    url: "#test-link"
    btn_label: "Read More"
    btn_class: "btn--primary"
---

{% include feature_row id="intro" type="center" %}

{% include feature_row %}

{% include feature_row id="feature_row2" type="left" %}

{% include feature_row id="feature_row3" type="right" %}

{% include feature_row id="feature_row4" type="center" %}
