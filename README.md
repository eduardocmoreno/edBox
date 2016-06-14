# edBox
Popup jQuery Plugin

#### How to use?
1º - Call jQuery, edBox plugin and css
```html
<link rel="stylesheet" href="your-css-directory/edbox.css">
<script src="http://code.jquery.com/jquery-latest.min.js"></script>
<script src="your-js-directory/edbox.js"></script>
```
2º - Initialize the plugin
```html
<script>
//Callback after document ready
$(document).ready(function(){
	//Initiazile plugin
	$('.elemClass').edbox();
	
	//Initiazile plugin as a callback function
	$.edbox({
		content: "#target"
	});
	
	//Initiazile plugin with your preferences
	//Check for other options at options list below
	$('.elemClass').edbox({
		content:'page.php?id=plugin',
		height:300,
		width:700,
		fx: 'fade',
		duration: 1000,
		onOpen: function(){
			alert("That's it!")
		}
	});
});
</script>
```
3º - Make the html structure like this:
```html
<!-- Call a DOM elem with an especific ID -->
<a class="elemClass" href="#target">open box</a>

<!-- Call an external content with parameters  -->
<a class="elemClass" href="page.php?par=parameter">load content</a>
```

#### Options
Option | Default Value | Description
--- | --- | ---
content | null | html, text, images or external pages
width | null | Fixed width
height | null | Fixed height
prefixId | box | Change this to create your own skin
htmlClose | &lt;img src="images/close-modal.png"/&gt; | html, text or images
header | null | Header content
footer | null | Footer content
beforeOpen | function() {}  | Callback before open
beforeClose | function() {}  | Callback before close
onOpen | function() {} | Callback after open
onClose | function() {}, | Callback after close
disableClose | false | Disable / enable close function
imgLoad | images/box-load.gif | Load image url location
animation | true | Disable / enable animations
fx | slide | Animation type (slide, fade or toggle)
duration | fast | Animation duration (fast, slow or set milisseconds)
easing | swing | Animation easing <br> require jQuery easing plugin - http://gsgd.co.uk/sandbox/jquery/easing/

#### Change Log
version 1.1
* New: option ID
* New: option animation (boolean)
* New: option duration
* New: option easing
* Improved: Dimensions setup
* Improved: Scroll functions

version 1.2
* New: Added $.edbox() function
* New: Added animation types (slide, fade and toggle)
* Fixed: close modal while loading issue

version 1.3
* New: option onClose callback

version 1.4
* New: option disableClose
* New: method to call closeBox function with callback
* Changed: option "close" to "htmlClose"
* Changed: option "boxClass" to "className"
* Fixed: issue getting dimensions of the content
* Fixed: centering load image when using padding
* Fixed: content validation when using html
* Removed: option bgColor
* Removed: option overlayBgColor

version 1.5
* improved: setting dimensions to the window

version 1.6
* New: option onOpen callback
* New: header and footer
* Changed: option className to prefixId

version 1.7
* New: option beforeOpen callback
* New: option beforeClose callback
* Change: Content option treatment for DOM elements
