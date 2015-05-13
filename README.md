# Mothership Carousel

The standard carousel for [Mothership](http://www.mothership.ec) sites.

## Basic usage

This library exposes a JQuery carousel function: `carousel(options)`. A carousel is defined in the markup as a list of images within a block element. Calling `.carousel()` on the JQuery element will transform it into a carousel. Additional options may be passed into the carousel function.

```html
<section class="carousel" id="carousel">
  <ul class="slides">
    <li>
      <img src="img/slide1.jpg">
    </li>
    <li>
      <img src="img/slide2.jpg">
    </li>
    <li>
      <img src="img/slide3.jpg">
    </li>
  </ul>
</section>

<script>
  window.carousel1 = $('#carousel1').carousel();
</script>
```

The image inside of each the slides may also be defined in a data attribute. For example 
```html
<li data-image="img/slide1"></li>
```
would work in the same way.

## Navigation

There are three main ways to navigate the carousel: arrows, dots and thumbnails. Only arrows are enabled by default.

Arrows may be disabled by setting the `useArrows` option to false: `$('#carousel').carousel({ useArrows: false })`.

Similarly the "dots" and "thumbnails" can be enabled by setting the `useDots` and the `useThumbs` option to true. When enabling thumbnails you should also set the image to use as the thumbnail with a data attribute as well as which element should be used for the thumbnails.

Using thumbnails:
```html
<section class="carousel" id="carousel" data-thumbs="#thumbs">
  <ul class="slides">
    <li data-thumb="img/thumbs/6_thumb.jpg">
      <img src="img/normal/6_norm.jpg">
    </li>
    <li data-thumb="img/thumbs/2_thumb.jpg">
      <img src="img/normal/2_norm.jpg">
    </li>
    <li data-thumb="img/thumbs/3_thumb.jpg">
      <img src="img/normal/3_norm.jpg">
    </li>
    <li data-thumb="img/thumbs/4_thumb.jpg">
      <img src="img/normal/4_norm.jpg">
    </li>
    <li data-thumb="img/thumbs/5_thumb.jpg">
      <img src="img/normal/5_norm.jpg">
    </li>
    <li data-thumb="img/thumbs/7_thumb.jpg">
      <img src="img/normal/7_norm.jpg">
    </li>
  </ul>
</section>
<div id="thumbs" class="carousel thumbs"></div>

<script>
  window.carousel2 = $('#carousel').carousel({ useThumbs: true });
</script>
```

This will generate a new carousel in the thumbnail element and link it's slides to the controls.

## Options

The options that may be passed in are as follows:

- useArrows(true): Show arrows if true.
- arrowLeft(undefined): The element to use as the left arrow control, If not set and useArrows is true, arrows will be generated.
- arrowRight(undefined): The element to use as the right arrow control, If not set and useArrows is true, arrows will be generated.
- useThumbs(false): Use thumbnail navigation if true.
- thumbElement(undefined): The element to use for thumbs. This may be set using the 'data-thumbs' attribute.
- animation(object)
  - type('slide'): The type of animation to use, slide and none are available by default. More may be added by setting the 'animations' option.
  - speed(500): The animation speed
- animations(object): An object containing the functions defining animations.
- imagesPerSlide(1): The number of images to show at any one time.
- allowZoom(false): Allows zoom to a larger view if true.
- zoomElement(undefined): The element to insert the larger image view into. If undefined an element will be inserted after the carousel.
- hideCarouselOnZoom(true): Hide the carousel when a zoom happens.
- hideThumbsOnZoom(true): Hide the thumbnails when a zoom happens.
- thumbConfig(undefined): The config to use when creating the Thumbnail carousel. It may take all the same options as the regular carousel.