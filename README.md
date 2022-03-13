# jQuery Offcanvas

**jQuery Offcanvas** is the easy way to arrange overloaded websites or to design user-friendly mobile navigations.

Set oversized content as off-canvas and let it flow-in, if needed - simple.

Take a look at the [project page](http://christoph-heich.de/jquery.offcanvas/) to see full documentation.

## Features
 * Completely responsive
 * Built-in touch/swipe support (comming soon)
 * Control of the entire behavior with lots of options
 * Fall-back for non-javascript users (will just don't do anything)
 * Lightweight - both, CSS and JS, just ~??? KB (minified and gzipped)

## Setup

### 1. Link files

Include [jquery.offcanvas.min.js](https://github.com/cheich/jquery.offcanvas/blob/master/build/js/jquery.offcanvas.min.js) and [jquery.offcanvas.min.css](https://github.com/cheich/jquery.offcanvas/blob/master/build/css/jquery.offcanvas.min.css) after the jQuery library.

``` html
<script src='jquery.min.js'></script>
<script src='jquery.offcanvas.min.js'></script>
<link rel="stylesheet" href="jquery.offcanvas.min.css" />
```

### 2. Identify main canvas

It's required to set a main canvas. By default it's `#page`. You can wrap the whole page with `div#page` or set the main canvas selector via `mainCanvas`. **Important:** It's not allowed to set `body` as main canvas.

``` javascript
$(document).ready(function() {
    $("#offcanvas-box").offcanvas({
        mainCanvas: '#page', // Selector or jQuery object
    });
});
```

### 3. Initialization and usage

After initialization, call a public method like `show`, `hide` or `toggle`.

``` javascript
$(document).ready(function() {
    $("#offcanvas-box").offcanvas(/* Pass options as object */); // Initialization

    $("button#toggle").click(function() {
        $("#offcanvas-box").offcanvas("toggle"); // Toggle after click a button
                                                 // Options are bound to the element
    });
});
```

## Dependencies

*jQuery Offcanvas* requires jQuery 1.7.0+. Certainly, it works with jQuery 2.x as well.

It is not necessary, but the animations are much smoother with the newest version of [jQuery Transit](https://github.com/rstacruz/jquery.transit).

## Options

To see the full documentation, go to the [project page](http://christoph-heich.de/jquery.offcanvas/). These are the default options:

``` javascript
defaults = {
    /* Off-canvas */
    position:          'left', // top|right|bottom|left
    mode:              'push', // push|cover|base
    injectPosition:    'before', // before|after, relative to main canvas
    cloneElement:      false, // Instead of moving it
    css:               { // Applied to the off-canvas wrapper
        width:  '100%',
        height: '100%'
    },
    jsFallback:        true, // If browser doesn't support CSS3 transitions or Transit isn't available
    animate:           {}, // Add further animation properties/options
    
    /* Main canvas */
    mainCanvas:        '#page', // Selector or jQuery object
    mainCanvasClick:   true, // Make the main canvas click-able
    mainCanvasAnimate: {}, // Add further animation properties/options - Overwrites 'animate'
    mainCanvasCss:     {}, // Add CSS styles to the main canvas
    
    /* Callbacks */
    onShowBefore:      function() {}, // Triggered before the off-canvas is shown
    onShowAfter:       function() {}, // Triggered after the off-canvas is shown
    onHideBefore:      function() {}, // Triggered before the off-canvas is hidden
    onHideAfter:       function() {}, // Triggered after the off-canvas is hidden
    onMainCanvasClick: function() {}, // Triggered after clicking on the main canvas
};
```

## Release notes
Each major release is mostly backward-compatible.
See the [history](https://github.com/cheich/jquery.offcanvas/blob/master/HISTORY.md) to see all changes and fixes.

## Support
Found some issues? Create and issue with the [issue tracker](https://github.com/cheich/jquery.offcanvas/issues).

## License
*jQuery Offcanvas* is released under the [MIT license](https://github.com/cheich/jquery.offcanvas/blob/master/LINCENSE.md)
