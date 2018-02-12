# TODO:

- small transparent border in logo
- slack e-mail in navigation and slack page
  - check if subject is filled in on windows
- check if reverting to jekyll 3.5 allows custom masthead.html again
- get navigation and/or toc working on organization page (https://mmistakes.github.io/minimal-mistakes/docs/helpers/#table-of-contents and https://mmistakes.github.io/minimal-mistakes/docs/overriding-theme-defaults/)
- external links

- ~web team~
- ~reduce size of images~
- open FB/twitter in new tab (external links https://mmistakes.github.io/minimal-mistakes/docs/docs-2-2/)
- ~disable FB comments~ later enable if it works...
- bart bio
-  /categories/
- homepage points to //
- Something weird is going on when pushing updates directly. Local changes aren't reflected. E.g. student-symposium tag removal in post about BBC17.
- Recent posts https://github.com/mmistakes/minimal-mistakes/issues/1251
- non greedy navigation https://github.com/mmistakes/minimal-mistakes/issues/902

# Overwriting theme defaults

Where to find `_data`, `_includes` and `_layouts`: run `bundle show minimal-mistakes-jekyll` and copy them to page directory.

# Including e-mail in footer
Edit `_includes/footer.html` by adding:

```
    <li><strong>Contact: </strong></li>
    {% if site.author.email %}
      <li><a href="mailto:{{ site.author.email }}"><i class="fa fa-fw fa-envelope" aria-hidden="true"></i> Email</a></li>
    {% endif %}
```

And comment out:

```
    <!-- {% if site.data.ui-text[site.locale].follow_label %}
      <li><strong>{{ site.data.ui-text[site.locale].follow_label }}</strong></li>
    {% endif %} -->
```

## Include Slack in footer

```
<li><a href="mailto:rsg-belgium@iscbsc.org?Subject=RSG%20Slack%20Subscription&Body=I%20would%20like%20to%20join%20the%20RSG%20Belgium%20Slack%20channel%2E"><i class="fa fa-fw fa-slack" aria-hidden="true"></i> Slack</a></li>
```

# Masthead with e-mail links

Add condition in `_includes/masthead.html`:

```
{% elsif link.url contains 'mailto' %}
    {% assign domain = '' %}
```

**NOTE**: in new version this breaks the masthead button, unless the entire `_sass` (and `_includes`?) folder are copied to the local directory. The `jekyll-data` plugin only seems to work for the `_data` folder.

# Custom CSS

In `assets/css/main.scss` add:

---
# Only the main Sass file needs front matter (the dashes are enough)
---

```
@charset "utf-8";

@import "minimal-mistakes/skins/{{ site.minimal_mistakes_skin | default: 'default' }}"; // skin
@import "minimal-mistakes"; // main partials

// $primary-color: #378973 !default;
$primary-color: #0d9ea5 !default;

.author__avatar {
  display: table-cell;
  vertical-align: top;
  width: 36px;
  height: 36px;

  @include breakpoint($large) {
    display: block;
    width: auto;
    height: auto;
  }

  img {
    max-width: 300px;
    border-radius: 10%;


    @include breakpoint($large) {
      padding: 5px;
      border: 1px solid $border-color;
    }
  }
}

// https://www.w3schools.com/howto/howto_css_hero_image.asp

.page__hero {
  position: relative;
  margin-bottom: 2em;
  @include clearfix;
  -webkit-animation: $intro-transition;
          animation: $intro-transition;
  -webkit-animation-delay: 0.25s;
          animation-delay: 0.25s;

  &--overlay {
    position: relative;
    margin-bottom: 2em;
    padding: 3em 0;
    @include clearfix;
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    -webkit-animation: $intro-transition;
            animation: $intro-transition;
    -webkit-animation-delay: 0.25s;
            animation-delay: 0.25s;

    a {
      color: #fff;
    }

    .wrapper {
      padding-left: 1em;
      padding-right: 1em;

      @include breakpoint($x-large) {
        max-width: $x-large;
      }
    }

    .page__title,
    .page__meta,
    .page__lead,
    .btn {
      color: #fff;
      text-shadow: 1px 1px 4px rgba(#000, 0.5);
    }

    .page__lead {
      max-width: $medium;
    }

    .page__title {
      font-size: $type-size-2;

      @include breakpoint($small) {
        font-size: $type-size-1;
      }
    }
  }
}

.page__hero-image {
  width: 100%;
  height: auto;
  -ms-interpolation-mode: bicubic;
}

.page__hero-caption {
  position: absolute;
  bottom: 0;
  right: 0;
  margin: 0 auto;
  padding: 2px 5px;
  color: #fff;
  font-family: $caption-font-family;
  font-size: $type-size-7;
  background: #000;
  text-align: right;
  z-index: 5;
  opacity: 0.5;
  border-radius: $border-radius 0 0 0;

  @include breakpoint($large) {
    padding: 5px 10px;
  }

  a {
    color: #fff;
    text-decoration: none;
  }
}
```

`_page.scss` contains layout for hero image banner.

to fix the RSG Belgium logo's rounded edges in author avatar.

https://github.com/spinnaker/spinnaker.github.io/blob/master/_sass/_page.scss
https://www.w3schools.com/howto/howto_css_hero_image.asp
https://html.com/attributes/img-width/
https://mademistakes.com/articles/jekyll-style-guide/

width
https://mmistakes.github.io/minimal-mistakes/docs/stylesheets/
https://github.com/mmistakes/minimal-mistakes/issues/74
https://github.com/mmistakes/minimal-mistakes/issues/433
https://github.com/mmistakes/minimal-mistakes/issues/884

# New feature_row_posts for main page

Create the following file in `_includes` and name it `feature_row_posts` without an extension.

See: https://github.com/mmistakes/minimal-mistakes/issues/1251

```
<div class="feature__wrapper">

  {% for f in site.posts limit:3 %}

  {% for f in feature_row_posts %}

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
  {% endfor %}

{% endfor %}
</div>
```

# buttons
https://mmistakes.github.io/minimal-mistakes/docs/utility-classes/#buttons

# image guidelines

For the images on the organization page, resize images to 400x450 pixels.

`convert daniele2.jpg -resize '800x400' -gravity center -crop '800x400+100+10' daniele2-rescaled.png`

`convert sander.png -resize '400x400' -gravity east -crop '400x400+20+0' sander-rescaled.png`

`convert bart.JPG -gravity Center -crop '2000x2200+0+0' bart-rescaled.png`

# General tips

## Escaping characters in YAML

https://stackoverflow.com/questions/11301650/how-to-escape-indicator-characters-i-e-or-in-yaml

https://symfony.com/doc/current/components/yaml/yaml_format.html

http://docs.octoprint.org/en/master/configuration/yaml.html

As simple rule of thumb, if your data contains any of these characters `:-{}[]!#|>&%@` better quote it.

In double quoted strings if you need to include a literal double quote in your string you can escape it by prefixing it with a backslash \ (which you can in turn escape by itself). In single quoted strings the single quote character can be escaped by prefixing it with another single quote, basically doubling it. Backslashes in single quoted strings do not need to be escaped.

```
'A single quote '' inside a single-quoted string'

"some quoted string with a : colon and a { bracket and a quote \" and a backslash \\ - phew"

'some single quoted string with a single quote '' and a backslash \ - yay'

"and a multiline string - just because we can we'll make it span
  across not two but four YAML lines!

  Including this paragraph. But in fact it will only be two lines :)"
```

HTML entities?
Different YAML specs?

https://stackoverflow.com/questions/32991517/how-to-escape-colons-and-other-special-characters-in-a-yaml-string

# Custom dropdown menu

https://github.com/mmistakes/minimal-mistakes/issues/1524



