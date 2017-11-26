# TODO:
- ~web team~
- ~reduce size of images~
- open FB/twitter in new tab (external links https://mmistakes.github.io/minimal-mistakes/docs/docs-2-2/)
- ~disable FB comments~ later enable if it works...

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

# Custom CSS

In `assets/css/main.scss` add:

```
// $primary-color: #378973 !default;

@charset "utf-8";

@import "minimal-mistakes/skins/{{ site.minimal_mistakes_skin | default: 'default' }}"; // skin
@import "minimal-mistakes"; // main partials

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

# buttons
https://mmistakes.github.io/minimal-mistakes/docs/utility-classes/#buttons

# image guidelines

For the images on the organization page, resize images to 400x450 pixels.

`convert daniele2.jpg -resize '800x400' -gravity center -crop '800x400+100+10' daniele2-rescaled.png`

`convert sander.png -resize '400x400' -gravity east -crop '400x400+20+0' sander-rescaled.png`

`convert bart.JPG -gravity Center -crop '2000x2200+0+0' bart-rescaled.png`
