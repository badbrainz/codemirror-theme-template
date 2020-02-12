# codemirror-theme-template
Create a CodeMirror syntax theme based on a set of CSS variables.

## Instructions
**Step 1: Setup a project**
1. Clone the Git repository.
2. Download and extract CodeMirror. https://codemirror.net/doc/releases.html
3. Edit property declarations in _variables.css_

**Step 2: Setup a CodeMirror instance**
```html
<link rel="stylesheet" href="codemirror/lib/codemirror.css">
<link rel="stylesheet" href="codemirror-theme-template/variables.css">
<link rel="stylesheet" href="codemirror-theme-template/tokens.css">
<script src="codemirror/lib/codemirror.js"></script>
<script>
CodeMirror(element, {...})
</script>
```

## Prototype with DevTools

![screenshot](https://user-images.githubusercontent.com/10160581/71879201-5bda5980-30e2-11ea-9d0d-2428b7597cb4.jpg)

**Step 1: Setup a workspace**
1. Open a browser tab and visit the HTML page.
2. Open the browser **DevTools**.
3. Switch to the **Sources** panel.
4. Click the **Overrides** tab.
5. Click **Select folder for overrides**.
6. Select a folder where your work will be saved.
7. Click **Allow** to give DevTools read/write access to the directory.

**Step 2 (optional): Track changes**
1. Expand the bottom drawer.
2. Click the **Changes** tab.

**Step 3: Edit the CSS variables**
1. Switch to the **Network** panel.
2. Open a context-menu for the **variables.css** file.
3. Click **Open in Sources panel**.
3. Change the color values using the inline color picker.
4. Save your work.
