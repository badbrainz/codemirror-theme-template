# codemirror-theme-template
Create a CodeMirror syntax theme based on a set of CSS variables.
## Instructions
**Download and extract CodeMirror**

https://codemirror.net/doc/releases.html

**Create an HTML file**
```html
<link rel="stylesheet" href="variables.css">
<link rel="stylesheet" href="tokens.css">
```

**Create a JavaScript file**
```js
CodeMirror(element, {
  lineNumbers: true,
  // etc...
})
```

**Visit the HTML page and make live edits to `variables.css` using your browser's DevTools**
* From the _Sources_ tab, select _Filesystem_ > _Add folder to workspace_.
* To revert changes, enable the _Changes_ tab in the bottom drawer.

![sc1](https://user-images.githubusercontent.com/10160581/71793601-51d92d80-2ff2-11ea-8e02-a927fb612439.png)
