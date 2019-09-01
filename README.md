# Stencil component in Vue


This is a step by step guide, how we can use a stencil component in a Vue app. For more details you can also check the official [Framework integration guide](https://stenciljs.com/docs/vue).

This project is created with [Vue Cli](https://cli.vuejs.org/)

## Similar guides
I have created another framework integration guide to use stencil components

* [Stencil components in React](https://github.com/ranjeetsinghbnl/stenciljs-react)
* [Stencil components in Angular](https://github.com/ranjeetsinghbnl/stenciljs-angular)
* [Stencil components in javascript](https://github.com/ranjeetsinghbnl/stenciljs-javascript)

In order to use the custom element library within the Vue app, the application must be modified to define the custom elements and to inform the Vue compiler which elements to ignore during compilation. This can all be done within the `main.js` file.

This example use the stencil component from the following project

* [Product & Cart showcase example](https://github.com/ranjeetsinghbnl/product-mgmt-stenciljs)

## Table of contents
* [Add the component to the dependencies](#add-the-component-to-the-dependencies )
* [Import the component](#import-the-components)
* [Consume the component](#consume-the-component)
* [Using component](#using-component)


## Add the component to the dependencies
Add the component to the app dependencies in `package.json`

```json
// package.json

"dependencies": {
  ...
  "@ranjeetsinghbnl/product-mgmt-stenciljs": "0.0.1"
}
```
or
Install it `npm install @ranjeetsinghbnl/product-mgmt-stenciljs`

## Import the component
import the component in the `main.js` file

```javascript
import {
  applyPolyfills,
  defineCustomElements as defineProductMgmtExp
} from '@ranjeetsinghbnl/product-mgmt-stenciljs/loader';
```

## Consume the component
Telling Vue to ignore the custom element tags [see](https://vuejs.org/v2/api/#ignoredElements). Add the following code to your `main.js` file. You can also use the component names or regular expression for that.

```javascript
Vue.config.ignoredElements = [/mf-\w*/];
```
or

```javascript
Vue.config.ignoredElements = [
    'mf-product-view',
    'mf-product-cart'
];
```
and Bind the custom elements to the window object

```javascript
applyPolyfills().then(() => {
  defineProductMgmtExp(window);
});
```

## Using component
Now The components should then be available in any of the Vue components

You can use it

```html
<mf-product-view></mf-product-view>
```

```html
<mf-product-cart></mf-product-cart>
```

To know more about the components. Please check the [Product & Cart showcase example](https://github.com/ranjeetsinghbnl/product-mgmt-stenciljs)


**Note: I have include the bootstrap 4 css to give style to the stencil components. Because they are open to design changes. Their is no style added to components i have used in the showcase**

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Run your tests
```
npm run test
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
