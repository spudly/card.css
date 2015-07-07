# card.css

CSS for displaying a flippable card that looks like a real index card.

# Running the Demo

To compile the CSS and open the demo html file in your default web browser, run the following commands:

```bash
git clone https://github.com/spudly/card.css.git
cd card.css
npm run demo
```

# Usage

Requires postcss and the following plugins:

* postcss-nested

You should pull it into your own stylesheet using the postcss-import plugin, like so:

```css
@import 'card.css';
```

Then you can build your css like so:

```javascript
var postcss = require('postcss');
postcss([
  require('postcss-import')(),
  require('postcss-nested')()
])
  .process(css, { from: 'src/app.css', to: 'app.css' })
  .then(function (result) {
    fs.writeFileSync('app.css', result.css);
    if (result.map) {
      fs.writeFileSync('app.css.map', result.map);
    }
  });
```
