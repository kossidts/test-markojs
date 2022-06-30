# Testing the Markojs Framework

## Reproduction of the scss bug

```sh
$ npm init marko
# enter the project name - e.g. test-marko
# wait for it...
$ cd test-marko
# install required sass modules in order to use scss
$ npm i -D sass-loader sass
$ npm run dev
# open the test-marko in an editor - e.g. VSCode
```

The App is up and running...

-   (Make some adjustments to the template files to meet your needs)
-   change the `style` block located in `src/components/app-layout/index.marko` into a `style.scss` block and write some scss code with nested selectors...

The App is still up and running...

-   Now create a scss folder and at least one partial:

```sh
$ cd test-marko
$ mkdir src/scss
$ touch src/scss/\_resets.scss
```

-   Now update the `style.scss` block to use the partial, e.g.

```scss
style.scss {
    @use "../../scss/resets";

    // ... more styles...
}
```

After saving the file the app might still be up and running. Now make a change to the `_resets.scss` partial file and save it. The app compilation of the styles should fail by now. If not just resave the file. Although the app itself is still (might still be) running the style is broken.

---

# Installation / creation of a new project

```
npx @marko/create marko-app --template basic
cd marko-app
npm install
npm run dev
```

## Overview

This project is powered by `@marko/serve` and `@marko/build`.

-   Run `npm run dev` to start the development server
-   Run `npm run build` to build a production-ready node.js server
-   Run `npm start` to run the production server

## Adding Pages

Pages map to the directory structure. You can add additional pages by creating files/directories under `src/pages` with `.marko` files. Learn more in the [`@marko/serve` docs](https://github.com/marko-js/cli/blob/master/packages/serve/README.md).
