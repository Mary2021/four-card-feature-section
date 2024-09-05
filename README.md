# Frontend Mentor - Four card feature section solution

This is a solution to the [Four card feature section challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/four-card-feature-section-weK1eFYK). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Preview](#preview)
  - [Repo and live URL](#repo-and-live-URL)
- [My process](#my-process)
  - [Built with](#built-with)
  - [Useful links](#useful-links)
- [Vitejs + Vue 3](#vitejs--vue-3)
- [Add Vuetify to Vitejs/Vue app](#add-vuetify-to-vitejsvue-app)
- [Install collection of utility functions](#install-collection-of-utility-functions)
- [Deploy to gh-pages](#deploy-to-gh-pages)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size

### Preview

![](./design/desktop-preview.jpg)

### Repo and live URL

- [Github repo](https://github.com:Mary2021/four-card-feature-section.git)
- [Live URL](https://mary2021.github.io/four-card-feature-section/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- CSS grid
- Mobile-first workflow
- Vitejs (the Composition API) + Vue

### Useful links

- [An Interactive Guide to CSS Grid](https://www.joshwcomeau.com/css/interactive-guide-to-grid/#alignment-9)
- [Options API vs Composition API](https://vueschool.io/articles/vuejs-tutorials/options-api-vs-composition-api/)
- [useWindowSize](https://vueuse.org/core/useWindowSize/)
- [useScreenOrientation](https://vueuse.org/core/useScreenOrientation/)
- [ScreenOrientation: change event](https://developer.mozilla.org/en-US/docs/Web/API/ScreenOrientation/change_event)
- [The Key-Changing Technique](https://michaelnthiessen.com/force-re-render/)

## Vitejs + Vue 3

- [Quick start](https://vuejs.org/guide/quick-start.html)

`npm create vue@latest`

This template should help get you started developing with Vue 3 in Vite.

### Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

### Type Support for `.vue` Imports in TS

TypeScript cannot handle type information for `.vue` imports by default, so we replace the `tsc` CLI with `vue-tsc` for type checking. In editors, we need [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) to make the TypeScript language service aware of `.vue` types.

### Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

### Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Type-Check, Compile and Minify for Production

```sh
npm run build
```

### Run Unit Tests with [Vitest](https://vitest.dev/)

```sh
npm run test:unit
```

### Run End-to-End Tests with [Cypress](https://www.cypress.io/)

```sh
npm run test:e2e:dev
```

This runs the end-to-end tests against the Vite development server.
It is much faster than the production build.

But it's still recommended to test the production build with `test:e2e` before deploying (e.g. in CI environments):

```sh
npm run build
npm run test:e2e
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```

## Add Vuetify to Vitejs/Vue app

[Existing projects](https://vuetifyjs.com/en/getting-started/installation/#existing-projects)

## Install collection of utility functions

`npm install @vueuse/core`

## Deploy to gh-pages

[How to Deploy Your Vite/Vue app](https://mkay11.medium.com/how-to-deploy-your-vite-vue-3-application-in-github-pages-2023-2b842f50576a)

- add your reponame to vite.config.ts

```javascript
export default defineConfig({
  base: '/REPONAME/',
  plugins: [],
  resolve: {
    alias: []
  }
})
```

- remove dist directory from .gitignore list!
- `npm run build`
- commit changes!
- `git subtree push --prefix dist origin gh-pages` this command will push up your /dist into a new or existing gh-pages branch

For future deployments:

- `npm install gh-pages --save-dev`
- in your package.json add:

```javascript
"scripts": {
  ...
  "predeploy": "npm run build",
  "deploy": "gh-pages -d dist",
  ...
}
```

Now all you need to do is to run `npm run deploy` and your app is newly deployed to gh-pages.

## Author

- Website - [Mary P](https://github.com/Mary2021)
