# radiant
radiant is a very simple **html + css + javascript** lightbox

## Demo
Please see the `demo.html` file

There is also a [JS Fiddle demo here](https://jsfiddle.net/g0rb314/z43kjaqe/1/)


## Usage
Add the following HTML snippet (from the `radiant.tpl` file) somewhere in the body of your html:
```html
	<div id="radiant-lightbox">
	    <div id="radiant-lightbox-close">&#x274C;</div>
	    <div id="radiant-lightbox-container1">
	        <div id="radiant-lightbox-container">
	            <div id="radiant-lightbox-prev">&#10094;</div>
	            <span id="radiant-lightbox-slot"></span>
	            <div id="radiant-lightbox-next">&#10095;</div>
	        </div>
	    </div>
	    <div id="radiant-lightbox-text"></div>
	</div>
```

Then link in the `radiant.js` and `radiant.css` in the `<head>` of your html:
```html
    <link rel="stylesheet" type="text/css" href="radiant.css">
    <script src="radiant.js"></script>
```

Finally, mark ythe images that you want to display in the lightbox, by adding the class `radiant-lightbox-slide` to the image tag:
```html
	<img src="https://i.imgur.com/Lmcwhvum.jpg" data-src="https://i.imgur.com/Lmcwhvu.jpg" class="radiant-lightbox-slide">
```

If the image has a `data-src` attribute, the url of that attribute will be used as the source for the "full-size" lightbox display. Otherwise, the url in the `src` attribute will be re-used.
In the example above, the page will use the lower-resolution **Lmcwhvum.jpg** image, while the lightbox view will display the higher resolution **Lmcwhvu.jpg** image.

## User interaction

When the user clicks on one of the `radiant-lightbox-slide` marked images on your html page, the lightbox view will open and display that image's lightbox content. This will show the image in its original size if the image is smaller than the window, and will scale it down to fit if the image is larger than the window.

Once displayed, the slide content can be closed by clicking on the image.

If there is only one slide in the list, it can also be closed by clicking anywhere else on the window.
If there are more than one slide, clicking to the right and left of the displayed image will switch to the next or previous 
slide, respectively. Anywhere else will close the lightbox view.

Additionally, if there are more than one image to display, the lightbox view will show an index and total (eg. "2/3") count at the bottom of the page, as in indication to the user about where in the list of images they are now.

The lightview will show `<` and `>` icons to hint that clicking will go to the previous / next slide, and a red `x` to hint that clicking will close the lightbox view.

## How it works
The `radiant.js` script will instantiate a `Radiant` object when the window is ready to be displayed.

The `Radiant` object will find all content that has the class `radiant-lightbox-slide`, and add it to a list of slides it can display. Each slide element gets an onclick handler that will call the `Radiant` object to display it in the lightbox view.

If the slide is an image with a `data-src` attribute, the url of that attribute will be used as the source
for the "full-size" lightbox display. Otherwise, the url in the `src` attribute will be re-used.

## Does it to {FEATURE}?

No, probably not. This is a simple lightbox solution:

* It will group all marked images into a single list.
* It does not add a link to the lightbox view image.
* It does not do a caption underneath images.

Maybe I'll add these features. Maybe you can. Fork it!

## Help, I don't have javascript enabled
No problem, it just won't work. It won't interfere either.
