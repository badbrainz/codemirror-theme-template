# codemirror-theme-template
Create a CodeMirror syntax theme based on a set of CSS variables.
```html
<link rel="stylesheet" href="variables.css">
<link rel="stylesheet" href="tokens.css">
```
## Instructions
Specify your colors (see *variables.css*):
```css
.cm-s-mytheme {
  --cm-atom       : hsl(39, 67%, 69%);
  --cm-attribute  : hsl(39, 67%, 69%);
  --cm-background : hsl(220, 10%, 18%);
  --cm-bracket    : hsl(355, 65%, 65%);
  --cm-builtin    : hsl(0, 0%, 40%);
  /* etc. */
}
```

Initialize CodeMirror:
```js
CodeMirror(element, {
  'theme': 'mytheme'
})
```
----
The same can be acheived with [Constructable Stylesheets](https://wicg.github.io/construct-stylesheets/).


```css
/* dark.css */
.CodeMirror {
  /* specify colors */
}
```
```css
/* lite.css */
.CodeMirror {
  /* specify colors */
}
```
```js
// Load reusable styles into CSSStyleSheet objects
function importStyles(styles) {
  const sheet = new CSSStyleSheet()
  const css = [styles].flat().map(url => `@import url("${url}");`).join('\n')
  return sheet.replace(css)
}

// Load required styles
let baseCSS = importStyles([
  '/libs/codemirror/lib/codemirror.css',
  '/variables.css',
  '/tokens.css'
])

// Load alternate colors
let darkCSS = importStyles('/dark.css')
let liteCSS = importStyles('/lite.css')

// Redefine css variables with a CSSStyleSheet object
async function setStyle(css) {
  document.adoptedStyleSheets = [
    await baseCSS,
    await css
  ]
}

async function main() {
  document.adoptedStyleSheets = [await baseCSS]
  CodeMirror(element)
  
  toggleDark.addEventListener('click', () => setStyle(darkCSS))
  toggleLight.addEventListener('click', () => setStyle(lightCSS))
}

main()
```
