# edBox
Popup jQuery Plugin

#### How to use?
1º - Call jQuery, edBox plugin and css inside **HEAD** tag
```html
<link rel="stylesheet" href="your-css-directory/edbox.css">
<script src="http://code.jquery.com/jquery-latest.min.js"></script>
<script src="your-js-directory/edbox.js"></script>
```
2º - Initialize the plugin (still inside **HEAD** tag)
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
3º - Inside **BODY** tag, make the html structure like this:
```html
<!-- Call an DOM elem with an especific ID -->
<a class="elemClass" href="#target">open box</a>

<!-- Call a external content with parameters  -->
<a class="elemClass" href="page.php?id=plugin">load content</a>
```

#### Options
Option | Default Value | Description
--- | --- | ---
content | null | Call the content (DOM elem ID, HTML, simple text, images, etc...)
width | null | Set a fixed width
height | null | Set a fixed height
prefixId | box | Set the name of the prefix ID (change this to use as a diferent skin)
htmlClose | img src="images/close-modal.png" | Set the close image tag with url location or html or text
header | null | Set the header content
footer | null | Set the footer content
beforeOpen | function() {}  | Callback before open
beforeClose | function() {}  | Callback before close
onOpen | function() {} | Callback after open
onClose | function() {}, | Callback after close
disableClose | false | Disable or enable close modal function
imgLoad | images/box-load.gif | Loading image url location
animation | true | Disable or enable animations
fx | slide | Animation type (slide, fade or toggle)
duration | fast | Set the animation duration (fast, slow or set milisseconds)
easing | swing | Set the easing motion (require jQuery easing plugin - http://gsgd.co.uk/sandbox/jquery/easing/)

#### Change Log
version 1.1
* New: added modal ID name option
* New: added enable/disable animation option
* New: added duration option
* New: added easing option
* Improved: Dimensions setup
* Improved: Scroll functions

version 1.2
* New: Added the $.edbox() function to be called as callback
* New: Added animation types (slide, fade and toggle)
* Fixed: issue when closing while loading

version 1.3
* New: added a callback (onClose) option

version 1.4
* New: option "disableClose" to disable closing events
* New: method to call closeBox function with callback
* Changed: option "close" to "htmlClose"
* Changed: option "boxClass" to "className"
* Fixed: issue getting dimensions of the content
* Fixed: centering load inmage when using padding
* Fixed: content type validation when using html tags
* Removed: bgColor option
* Removed: overlayBgColor option

version 1.5
* improved: setting dimensions to the window

version 1.6
* New: design
* New: added a callback (onOpen) option
* New: header and footer
* Changed: option className to prefixId

version 1.7
* New: option beforeOpen to fire a function before edbox begins to open
* New: option beforeClose to fire a function before edbox begins to close
* Change: if content is a dom element so now it will be moved into modal, instead cloned
