# codemirror-theme-template
Create a CodeMirror syntax theme based on a set of CSS variables.

![screenshot](https://user-images.githubusercontent.com/10160581/71861129-244fbb00-30aa-11ea-90bd-d109438adb32.jpg)

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
2. Open the browser **DevTools**
3. Switch to the **Sources** panel.
4. Click the **Overrides** tab.
5. Click **Select folder for overrides**.
6. Select the project folder.
7. Click **Allow** to give DevTools read/write access to the directory.

**Step 4 (optional): Track changes**
1. Expand the bottom drawer.
2. Click the **Changes** tab.

**Step 5: Edit the CSS variables**
1. Switch to the **Network** panel.
2. Open a context-menu for the **variables.css** file.
3. Click **Open in Sources panel**.
3. Change the color values using the inline color picker.
