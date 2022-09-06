# React FontAwesome Slim

## Disclaimer

This package exists to let bundle size be smaller. This is not an official package.
If you are looking for an official one, please, check here: [@fortawesome/react-fontawesome](https://www.npmjs.com/package/@fortawesome/react-fontawesome). This library is also created from [Eugene Zinovyev's react-fontawesome-svg-icon](https://github.com/eugenezinovyev/react-fontawesome-svg-icon).


## Motivation

Existing [@fortawesome/react-fontawesome](https://www.npmjs.com/package/@fortawesome/react-fontawesome) brings the whole [@fortawesome/fontawesome-svg-core](https://www.npmjs.com/package/@fortawesome/fontawesome-svg-core) into the final bundle, making the bundle size way bigger.

Existing [react-fontawesome-svg-icon](https://github.com/eugenezinovyev/react-fontawesome-svg-icon) made by Eugene Zinovyev also had its last update early this year. React 18, launched in late March was not included on its peer list.

This library was made to both support the latest version of React, while also making the bundle size smaller.

## How it works

The package uses icon vector data provided by Fontawesome SVG packages (e.g. `@fortawesome/free-solid-svg-icons` or `@fortawesome/free-regular-svg-icons`)
and styles from `@fortawesome/fontawesome-svg-core`.

It is important to include styles from `@fortawesome/fontawesome-svg-core` to the bundle to make it work.
Check [installation section](#installation) to more details.

## Example

```tsx
import React from 'react';
import { FontAwesomeSvgIcon } from 'react-fontawesome-svg-icon';
import { faCoffee } from '@fortawesome/free-solid-svg-icons';

const App = () => (
    <FontAwesomeSvgIcon icon={faCoffee} />
);

export default App;
```

Resulting HTML

```html
<svg xmlns="http://www.w3.org/2000/svg" role="img" viewBox="0 0 640 512" class="svg-inline--fa fa-coffee fa-w-20 fa-lg">
    <path fill="currentColor" d="M192 384h192c53 0 96-43 96-96h32c70.6 0 128-57.4 128-128S582.6 32 512 32H120c-13.3 0-24 10.7-24 24v232c0 53 43 96 96 96zM512 96c35.3 0 64 28.7 64 64s-28.7 64-64 64h-32V96h32zm47.7 384H48.3c-47.6 0-61-64-36-64h583.3c25 0 11.8 64-35.9 64z">
    </path>
</svg>
```

## Installation

Install `react-fontawesome-svg-icon`, `@fortawesome/fontawesome-svg-core` and required SVG icon packages.

```
npm install --save react-fontawesome-svg-icon @fortawesome/fontawesome-svg-core @fortawesome/free-regular-svg-icons @fortawesome/free-solid-svg-icons
```

```
yarn add react-fontawesome-svg-icon @fortawesome/fontawesome-svg-core @fortawesome/free-regular-svg-icons @fortawesome/free-solid-svg-icons
```

Import `@fortawesome/fontawesome-svg-core/styles.css` into the entry point.

```tsx
import React from 'react';
import ReactDOM from 'react-dom';
import '@fortawesome/fontawesome-svg-core/styles.css';
import App from './components/App';

ReactDOM.render(<App />, document.getElementById('root'));

```

## Feature Support

* [Different icon collections via importing icons from different SVG icon packages.](https://react-fontawesome-svg-icon.netlify.app/features#families)
* [Sizing Icons.](https://react-fontawesome-svg-icon.netlify.app/features#sizes)
* [Custom `className`, `style` and `color` props.](https://react-fontawesome-svg-icon.netlify.app/features#styling)
* [Fixed Width Icons.](https://react-fontawesome-svg-icon.netlify.app/features#fixed-width)
* [List Item Icons.](https://react-fontawesome-svg-icon.netlify.app/features#list-item)
* [Color Inversion.](https://react-fontawesome-svg-icon.netlify.app/features#inverse)
* [Pulled and Bordered icons.](https://react-fontawesome-svg-icon.netlify.app/features#pull-and-border)
* [Opacity Swap for Duotone icons.](https://react-fontawesome-svg-icon.netlify.app/features#swap-opacity)
* [Rotation.](https://react-fontawesome-svg-icon.netlify.app/features#rotation)
* [Flip.](https://react-fontawesome-svg-icon.netlify.app/features#flip)
* [Spin Animation.](https://react-fontawesome-svg-icon.netlify.app/features#animation)
* [Pulse Animation.](https://react-fontawesome-svg-icon.netlify.app/features#animation)
* [Icon Title.](https://react-fontawesome-svg-icon.netlify.app/features#title)
* [Tab Index.](https://react-fontawesome-svg-icon.netlify.app/features#tab-index)
* [Ref Forwarding.](https://react-fontawesome-svg-icon.netlify.app/features#ref-forwarding) Component is wrapped with `React.forwardRef`. The ref passed to the root SVG element.
* [SVG symbols.](https://react-fontawesome-svg-icon.netlify.app/features#svg-symbols)

Not supported yet: 
* `transform` property: [Power Transforms](https://fontawesome.com/how-to-use/on-the-web/styling/power-transforms)
* `mask` property: [Masking Icons](https://fontawesome.com/how-to-use/on-the-web/styling/masking)

## Bundle Size Comparison

A simple React application with `react-fontawesome-svg-icon` bundle compared to a similar application with `@fortawesome/react-fontawesome` bundle.

Baseline:
* main.js 173.42 kB (55.91 kB gzipped)
* main.css 619 B (372 B gzipped)

Comparison:
* main.js 141.57 kB (45.95 kB gzipped)
* main.css 6.79 kB (1.71 kB gzipped)

## main (-25,675 bytes)

|| Module | Count | Size |
|-|-|-|-|
|+|../../../../react-fontawesome-svg-icon/lib/index.esm.js|1|+1,574|
|+|css ../../../../../node_modules/css-loader/dist/cjs.js!../../../../../node_modules/@fortawesome/fontawesome-svg-core/styles.css|1|+7,891|
|-|../../../../../node_modules/@fortawesome/react-fontawesome/index.es.js|5|-91,949|
|-|../../../../../node_modules/@fortawesome/fontawesome-svg-core/index.es.js|1|-76,794|
|-|../../../../../node_modules/prop-types/index.js|3|-2,663|
|-|webpack/runtime/compat get default export|1|-267|
|-|webpack/runtime/define property getters|1|-308|
|-|webpack/runtime/global|1|-221|
|-|webpack/runtime/hasOwnProperty shorthand|1|-88|
|△|*1 modules with minor changes*| |+58|

