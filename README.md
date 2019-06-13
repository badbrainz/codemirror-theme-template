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
