# RSG Belgium website

## Making posts or announcements

Each post consists of a markdown file in the `_posts` directory. Each post should include a front matter:
```
---
layout: single
title:  "Second Bioinformatics Student Day - 13/10/2017 - Brussels"
date:   2017-10-02 19:10
categories: event student-symposium
---
```

For more information on how posts work, refer to the documentation of the Minimal Mistakes theme ([https://mmistakes.github.io/minimal-mistakes/docs/posts/](https://mmistakes.github.io/minimal-mistakes/docs/posts/)).

## Updating the website

To install all the Jekyll and Ruby requirements needed for building the site, see the theme's documentation [https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/) or the Jekyll docs [https://jekyllrb.com/docs/quickstart/](https://jekyllrb.com/docs/quickstart/)

The site can be checked locally by using the `bundle exec jekyll serve` command.

Use `bundle exec jekyll build` to create an updated version of the site ready for deployment. The resulting `_site` directory should be pushed to the `rsg-belgium.iscbsc.org​` domain.

Example work flow:

`rsync - --delete -e ssh _site/ rsgbelgium@rsg-belgium.iscbsc.org:/home/rsgbelgium/rsg-belgium.iscbsc.org/`

Omit the `-n` dry flag for an actual sync to occur. Don't forget the `/` at the end of the `_site` directory to push the *contents* of the directory rather than the directory itself.
