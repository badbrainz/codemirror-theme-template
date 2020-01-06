# codemirror-theme-template
Create a CodeMirror syntax theme based on a set of CSS variables.

![sc1](https://user-images.githubusercontent.com/10160581/71793601-51d92d80-2ff2-11ea-8e02-a927fb612439.png)

## Instructions
**Step 1: Download and extract CodeMirror**

https://codemirror.net/doc/releases.html

**Step 2: Setup a CodeMirror instance**
```html
<link rel="stylesheet" href="variables.css">
<link rel="stylesheet" href="tokens.css">
```
```js
CodeMirror(element, {
  lineNumbers: true,
  // etc...
})
```

**Step 3: Setup a workspace**
1. Open a browser tab and visit the HTML page.
2. Open DevTools (Cmd+Option+J (Mac) or Ctrl+Shift+J (Windows, Linux, Chrome OS)).
3. Click the **Overrides** tab.
4. Click **Select folder for overrides**.
5. Click **Add folder to workspace**.
6. Select the project folder.
7. Click **Allow** to give DevTools read/write access to the directory.

**Step 4 (optional): Track changes**
1. Expand the bottom drawer.
2. Click the **Changes** tab.

**Step 5: Edit the CSS variables**
1. Click the **variables.css** file.
2. Change the color values using the inline color picker.
