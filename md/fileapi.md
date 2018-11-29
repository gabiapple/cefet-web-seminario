### File API - Code

html
```html

<div class="container">
  <textarea id="file-content"></textarea>
    <label for="file">Selecione um arquivo</label>
    <input type="file" id="input-file" name="input-file" accept="text/">
  </div>
</div>
```

js
```js
document.getElementById('input-file').addEventListener('change', loadFile);

function loadFile(event) {
    const input = event.target
  if ('files' in input && input.files.length > 0) {
	  placeFileContent(document.getElementById('file-content'), input.files[0])
  }
}
function placeFileContent(target, file) {
    const reader = new FileReader();
    reader.onload = event => target.value = event.target.result;
    reader.readAsText(file);
}
```
