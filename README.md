# RSG Belgium website

## Creating posts or announcements

Each post consists of a markdown file in the `_posts` directory. Each post should include a front matter similar to this:
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

To install all the Jekyll and Ruby requirements needed for building the site, see the theme's documentation [https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/) or the Jekyll docs [https://jekyllrb.com/docs/quickstart/](https://jekyllrb.com/docs/quickstart/).

A very brief overview is:

1. Install a recent version of ruby. The easiest way is probably to install [`rbenv`](https://github.com/rbenv/rbenv) to install version 2.5.0.
2. Install `bundler` via: `gem install bundler`.
3. Install all Jekyll dependencies for the website by running `bundle install` inside the main directory (where the `Gemfile` is located).

The site can then be viewed locally by using the `bundle exec jekyll serve` command and navigating to the local server.

Use `bundle exec jekyll build` to create an updated version of the site ready for deployment. The resulting `_site` directory should be copied in its entirety to the `rsg-belgium.iscbsc.org​` domain.

Example work flow:

`rsync -Pvahn --delete -e ssh _site/ rsgbelgium@rsg-belgium.iscbsc.org:/home/rsgbelgium/rsg-belgium.iscbsc.org/`

Omit the `-n` dry flag for an actual sync to occur. Don't forget the `/` at the end of the `_site` directory to push the *contents* of the directory rather than the directory itself.

## Requirements

- minimal-mistakes-jekyll-4.9.1 (was 4.6.0)
- jekyll 3.7.2 (was 3.6.2)
- ruby 2.5.0 (installed via rbenv as desribed here: https://www.digitalocean.com/community/tutorials/how-to-install-ruby-on-rails-with-rbenv-on-ubuntu-16-04)
