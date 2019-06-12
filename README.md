# codemirror-theme-template
Create a CodeMirror syntax theme based on a set of CSS variables.
```html
<link rel="stylesheet" href="variables.css">
<link rel="stylesheet" href="tokens.css">
```
## Instructions
Specify your colors (see *variables.css*):
```css
/* dark.css */

.CodeMirror.cm-s-dark {
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
  theme: 'dark'
})
```
----
Theme toggling with Shadow DOM and CSS host-context:
```css
/* dark.css */

:host-context([data-theme-dark]) .CodeMirror {
  /* specify dark colors. */
}
```
```js
async function main() {
  const node = document.body

  let sheet = new CSSStyleSheet()
  sheet = await sheet.replace(`
    @import url("/codemirror/lib/codemirror.css");
    @import url("/variables.css");
    @import url("/tokens.css");
    @import url("/dark.css");
  `)

  node.attachShadow({ mode: 'open' })
  node.shadowRoot.adoptedStyleSheets = [await sheet]
  node.setAttribute('data-theme-dark', '')

  CodeMirror(node.shadowRoot)
}

main()
```
