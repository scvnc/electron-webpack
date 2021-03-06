To keep your `devDependencies` size minimal, only JavaScript is supported out of the box
(because even in a pure typescript project, JavaScript transpilation is required to import external dependencies on demand (e.g. ui libraries iView, Element)).

Special presets are used to ensure that you don't need to specify all required packages explicitly, — for example, `electron-webpack-ts` includes `ts-loader` and `fork-ts-checker-webpack-plugin` for you.
But if you want, you can install loaders/plugins explicitly (it will be still detected and appropriate config applied).

## JavaScript

Supported out of the box.
Babel plugins and polyfills that you need based on your used version are determined automatically using [babel-preset-env](https://github.com/babel/babel-preset-env).

## TypeScript

`yarn add typescript electron-webpack-ts --dev`

Create `tsconfig.json` in the project root directory:

```json
{
  "extends": "./node_modules/electron-webpack/tsconfig-base.json"
}
```

If you use Vue.js, create `vue-shims.d.ts` in the `src/renderer`

```typescript
declare module "*.vue" {
  import Vue from "vue"
  export default Vue
}
```

## Vue.js

`yarn add vue electron-webpack-vue --dev`

Please note — [Chrome devtools extension for debugging Vue.js applications](https://github.com/vuejs/vue-devtools) is automatically installed in a dev mode.

## React

`yarn add babel-preset-react --dev`

## iView

"Import on demand" feature is supported out of the box.

## Less

`yarn add less-loader less --dev`

## Sass

`yarn add sass-loader node-sass --dev`

## EJS

`yarn add ejs ejs-html-loader --dev`

## Next.js

If project has [electron-next](https://github.com/leo/electron-next) dependency, `electron-webpack dev` will not start webpack-dev-server.

To compile only main process, use `electron-webpack main`.

## Nunjucks

`yarn add nunjucks-loader nunjucks --dev`