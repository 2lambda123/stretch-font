<p align="center" style="text-align: center">
  <img width="300" style="max-width:100%;" alt="Stretch Font: The utility dynamically adjusts the font size based on the width and height of the container" src="https://lh3.googleusercontent.com/drive-viewer/AFGJ81r-pDRRmxLwqLVLWFXtdhL9B0bgj1YHe6otqqMJhc3gwexSm9TfPz8owrTSzPlkMFmW_zZewHzDJYp43QBhHtsYa1X6iA=s2560" />
</p>

<h1 align="center" style="text-align: center">Stretch Font</h1>

<div align="center" style="text-align: center">

[![npm](https://img.shields.io/npm/v/stretch-font)][npm-link]
[![npm](https://img.shields.io/npm/dt/stretch-font)][npm-link]
[![GitHub](https://img.shields.io/github/license/sarmaged/stretch-font)][github-link]

</div>

<p align="center" style="text-align: center">
<strong>The Utility Dynamically</strong><br />
Adjusts the <u>font size</u> depending on the <u>width</u> and <u>height</u> of the container.</p>

<hr>

<p>This plugin was created in order not to write CSS [Media query] rules for each screen when you have many languages and you can switch them dynamically.</p>

### Support
- 🥶 Freeze text in container
- 🤩 Watches when elements are added
- 🔥 Hot text replacement (i18n)
- 🖥 Any change in the width of the parent element
- 🔄 Rotate
- 📝 Multiline
- ✅ CSS Animation
- ✅ CSS Transition

<hr>

## Installation
```bash
npm install stretch-font
```
```bash
yarn add stretch-font
```

## Simple usage

#### For ES Module
```javascript
import 'stretch-font/style.css'
import stretchFont from 'stretch-font'

// Run only once if you didn't use "root"
// If you've used root many times, it should be different
stretchFont()
```

#### OR for HTML
```html
<link rel="stylesheet" href="https://unpkg.com/stretch-font/style.css">
<script src="https://unpkg.com/stretch-font/stretch-font.min.js"></script>
<script>stretchFont()</script>
```

## Usage
### Freeze
<p><strong>Perfect for inline elements (i18n)</strong><br />
<i style="color: #777">As if freezing the text inside the container</i></p>

```vue
<button class="stretch-font">{{ $t("done") }}</button>
...
<span class="stretch-font">{{ $t("message") }}</span>
```

<p><i style="color: #777">When you change the language, the text takes on the original block width and is not stretched. In this case, the font may increase or decrease depending on how long the text will be.</i>
</p>

### Stretch [ X & Y ]
<p><strong>Perfect for dynamically block elements</strong><br />
<i style="color: #777">When you need the text to be dynamically calculated from the <strong>width</strong> and <strong>height</strong> of the block</i></p>

```vue
<div class="SOME_DYNAMICALLY_BLOCK" :style="{ width: x + 'px', height: y + 'px' }">
  <div class="stretch-font" data-stretch>
    {{ $t("message") }}
  </div>
</div>
```

### Stretch [ X ]
<p><strong>Perfect for Block elements / CSS Animations / Transition</strong><br />
<i style="color: #777">Stretches the text only to the <strong>width</strong> of the container.</i></p>

```html
<div class="stretch-font" data-stretch-x>Some text...</div>
```

### Stretch [ Y ]
<p><strong>Perfect for Block elements</strong><br />
<i style="color: #777">Stretches the text only to the <strong>height</strong> of the container.</i></p>

```html
<div class="stretch-font" data-stretch-y>Some text...</div>
```

### Stretch [ min ] = n
<p><strong>Used for all elements</strong></p>

```html
<div class="stretch-font" data-stretch-min="10">
  Font size cannot be less than 10px
</div>
```

### Stretch [ max ] = n
<p><strong>Used for all elements</strong></p>

```html
<div class="stretch-font" data-stretch-max="20">
  Font size cannot be larger than 20px
</div>
```

## Options

### useStretchFont(root, className)
```
// defaults

root = document
className = "stretch-font"
```

## Mistakes
<p style="color: #FF7B42">⚠️ Do not apply styles and classes to the "stretch-font" block or inline element</p>

```html
🚫 Incorrect
<div class="stretch-font" style="font-size: 100px"> ... </div>

✅ Correct
<div style="font-size: 60px;">
  <div class="stretch-font">
    ...
  </div>
</div>
```
```html
🚫 Incorrect
<div class="stretch-font fz100">
  ... class fz100 - it's font-size: 100px ...
</div>

✅ Correct
<div class="fz100">
  <div class="stretch-font">
    ...
  </div>
</div>
```

## License
Distributed under the MIT License. See `LICENSE` for more information.

[npm-link]: https://www.npmjs.com/package/stretch-font
[github-link]: https://github.com/Sarmaged/stretch-font
