# sv

Everything you need to build a Svelte project, powered by [`sv`](https://github.com/sveltejs/cli).

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

```bash
# create a new project in the current directory
npx sv create

# create a new project in my-app
npx sv create my-app
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
NODE_ENV=development npm run dev

# or start the server and open the app in a new browser tab
NODE_ENV=development npm run dev -- --open
```

## Building

To create a production version of your app:

```bash
NODE_ENV=development npm run build
```

You can preview the production build with `NODE_ENV=development npm run preview`.

> To deploy your app, you may need to install an [adapter](https://svelte.dev/docs/kit/adapters) for your target environment.

# Publish SvelteKit project on GitHub Pages

## Install @sveltejs/adapter-static and gh-pages. 

```sh
npm i -D @sveltejs/adapter-static gh-pages
```

## Update svelte.config.js by changing adapter-auto to adaptor-static.

```js
import adapter from '@sveltejs/adapter-static';
```

## +layout.js

Add the following to `src/routes/+layout.js`

```js
export const prerender = true;
```

## Add a script to package.json. 

```json
"gh-pages": "npm run build && npx gh-pages -d build"
```

## Deploy

Now you just need to run `npm run gh-pages`.

## .nojekyll file for Tailwind CSS/Postcss

If you are using a postcss such as Tailwind css, you need to add **an empty `.nojekyll`** file to the `gh-pages` branch.
