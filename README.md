# vue-plugin-template

> ✨ DX experience & lighter plugins 🚀


## Usage

```bash
vue init posva/vue-plugin-template my-awesome-plugin
# Answer some questions
cd my-awesome-plugin
yarn
npm run dev
# 🎉
```

## Features

### Smaller plugin size
Bundle with [Rollup](https://github.com/rollup/rollup). This produces bundles
that are easier to debug and more lightweight but is less customizable than
Webpack. But don't worry **you can also use Webpack** instead of Rollup 😉

### Single file components
Write your components using `.vue` files. Those will be compiled into render
functions when building your plugin to make them compatible everywhere.

### JSX
Add jsx to your `js` files and they will be compiled as well.

### ES6
Use the future features of Javascript.

### Pre commit lint and fix
Runs `eslint` and `stylefmt`/`stylelint` before each commit on modified files
only and try to fix them automatically to prevent failing CI builds 😉.

### Advanced testing
Get the best developer experience by testing the components at the same
time you **interact** with them.
<details>
  <summary>Embrace Visual testing 😎</summary>
  ![visual testing](https://cloud.githubusercontent.com/assets/664177/21402771/504f94de-c7ba-11e6-9b10-3c9833a7e316.gif)
</details>

### Next generation CSS
Use [PostCSS](http://postcss.org/) by default with [CSSNext](http://cssnext.io/)
to bring you future features of CSS.

### SASS
You still need a preprocessor? Choose Webpack as the bundler and access more
advanced features

### Development-only features
Add warnings to improve the DX of your plugin that are removed when bundling in
production mode:

```js
if (process.env.NODE_ENV !== 'production' && warningCondition) {
  warn('You should be doing things this way instead: ...')
}
```
Refer to [Dist files](#dist-files) for more information.

## Road-map

- Add flow typings
- `.github` folder
- Add question for tests
- Add question for visual tests
- Add question for contribution guidelines 
- Add question for the license
- Add question for linting

**Something you would like to see on the template but not in the
road-map?
[Fire an Issue!](https://github.com/posva/vue-plugin-template/issues/new)**

## FAQ

### Dist files

_Q_: **Why are there 3 different generated files for js in the `dist` folder?**

_A_: Each one serves its purpose: the non minified file (`lib.js`) replaces `process.env.NODE_ENV` by `"development"` to keep development only features like warning (pretty much like Vue warnings). The CommonJS file (`lib.common.js`) is meant to be used with bundlers like Webpack or Rollup and keeps the variable `process.env.NODE_ENV` so it can be replaced by bundlers. The minified version (`lib.min.js`) strips off development features by replacing `process.env.NODE_ENV` by `"production"`.

_Q_: **When should I choose Rollup over Webpack for the bundler?**

_A_: If [next-css](http://cssnext.io/) isn't enough for you, it's better to use
Webpack. If a feature is missing
in [vue-rollup-plugin](https://github.com/vuejs/rollup-plugin-vue) but present
on [vue-loader](https://github.com/vuejs/vue-loader/) you can benefit from it by
using Webpack. On the other hand if you're building a simple plugin with few
components, you should use Rollup as the bundler to get more lightweight lib
sizes.

## Contributing


See [CONTRIBUTING.md](CONTRIBUTING.md) for help about developing this template

## License

[MIT](http://opensource.org/licenses/MIT)
