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
  --cm-atom       : hsl(39, 67%, 69%);
  --cm-attribute  : hsl(39, 67%, 69%);
  /* etc. */
}
```
```css
/* lite.css */
.CodeMirror {
  --cm-atom       : hsl(41, 99%, 30%);
  --cm-attribute  : hsl(41, 99%, 30%);
  /* etc. */
}
```
```js
// Load files into CSSStyleSheet objects
function importStyles(urls) {
  const sheet = new CSSStyleSheet()
  const css = [styles].flat().map(url => `@import url("${url}");`).join('\n')
  return sheet.replace(css)
}

// Create reusable css
let darkCSS = importStyles('/dark.css')
let liteCSS = importStyles('/lite.css')
let baseCSS = importStyles([
  '/libs/codemirror/lib/codemirror.css',
  '/variables.css',
  '/tokens.css'
])

// Swap colors by changing 'adoptedStyleSheets'
async function setStyle(documentOrShadowroot, css) {
  documentOrShadowroot.adoptedStyleSheets = [
    await baseCSS,
    await css
  ]
}

async function main() {
  await setStyle(document, darkCSS)
  CodeMirror(element)
  
  // await setStyle(document, liteCSS)
}

main()
```
