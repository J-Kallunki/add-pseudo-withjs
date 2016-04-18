# add-pseudo-withjs
Add pseudo content or background with JS and jQuery without reloading the DOM

In this example I'll add SVG to pseudo-element background:
```javascript
var jQ = $.noConflict();
var svg = "<svg xmlns='http://www.w3.org/2000/svg' width='100' height='100'> \
<linearGradient id='gradient'> \
<stop offset='0%' stop-color='#000'/> \
<stop offset='100%' stop-color='#AAA'/> \
</linearGradient> \
</svg>";
var svgURI = escape(svg);
var css = "<style>.testpseudo:before { background-image : url(\'data:image/svg+xml," +svgURI+ "\') }</style>";
jQ(css).appendTo("head");
jQ(".test").addClass('testpseudo');
```
