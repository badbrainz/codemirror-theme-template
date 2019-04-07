# codemirror-theme-template
Create a CodeMirror syntax theme based on a set of CSS variables.

## Instructions

Include the neccessary files:
```html
<link rel="stylesheet" href="variables.css">
<link rel="stylesheet" href="tokens.css">
```

Specify your colors using variables that are defined in *variables.css*:
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
