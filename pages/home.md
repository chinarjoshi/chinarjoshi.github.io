---
title: "Chinar Joshi"
layout: splash
permalink: /

header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: assets/images/splash.jpg
  actions:
    - label: "See on GitHub"
      url: "https://github.com/chinarjoshi"
  caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
intro:
 - excerpt: 'Welcome to my personal website, where you can see my projects, resume, and ways to contact me.'

feature_row:
  - image_path: /assets/images/blur-code.png
    alt: "Portfolio image"
    title: "Portfolio"
    excerpt: "My open source software products"
    url: "/portfolio/"
    btn_label: "Read More"
    btn_class: "btn--primary"
  - image_path: /assets/images/resume.png
    alt: "Resume image"
    title: "Resume"
    excerpt: "My experience and education"
    url: "/resume/"
    btn_label: "Read More"
    btn_class: "btn--primary"
  - image_path: /assets/images/contact.png
    alt: "Phone image"
    title: "Contact"
    excerpt: "How to reach me"
    url: "/contact/"
    btn_label: "Read More"
    btn_class: "btn--primary"
---

{% include feature_row id="intro" type="center" %}

{% include feature_row %}
