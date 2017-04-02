# add-pseudo-withjs
Add pseudo content or background with JS without reloading the DOM

In this example I'll add SVG to pseudo-element background:
```javascript
var svg = "<svg xmlns='http://www.w3.org/2000/svg' width='100' height='100'> \
<linearGradient id='gradient'> \
<stop offset='0%' stop-color='#000'/> \
<stop offset='100%' stop-color='#AAA'/> \
</linearGradient> \
</svg>";
var svgURI = escape(svg);
var css = "<style>.testpseudo:before { content: ''; display: inline-block; height: 1em; width: 20px; background-image : url(\'data:image/svg+xml," +svgURI+ "\') }</style>";
var temp = document.createElement('div');
temp.innerHTML = css;
var head = document.head;
while (temp.firstChild) {
	head.appendChild(temp.firstChild);
}
var el = document.getElementsByClassName("test");
el[0].classList.add("testpseudo");
```