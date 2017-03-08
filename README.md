# rollup-plugin-shebang

[![Greenkeeper badge](https://badges.greenkeeper.io/zeekay/rollup-plugin-shebang.svg)](https://greenkeeper.io/)

Rollup.js plugin which adds a unix-style shebang.

## Installation

```bash
npm install --save-dev rollup-plugin-shebang
```

## Usage

Add the following code to your project's `rollup.config.js`:

```js
import shebang from 'rollup-plugin-shebang';

export default {
  entry: 'index.js',
  plugins: [
    shebang()
  ]
};
```

## License

MIT
