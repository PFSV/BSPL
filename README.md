# Steet View Exploration Demo

## Introduction

[Try this demo! (Google Maps API key is needed)](https://constantjin.github.io/streetview_exploration_demo/)

Demo for Google Street View control (and capture) with a keyboard.

- W/D keys to control the viewpoint (heading).
- A/S keys to move forward(backward) following the link arrows in the map.
- F key to capture the current scene as an image.
- You need to generate a **Google Maps API key** beforehand for this demo
  - You can follow [this guide](https://developers.google.com/maps/documentation/javascript/get-api-key) to generate Google Maps API key.

This demo is built on **[React](https://reactjs.org/) + Typescript** and bundled using [**Vite**](https://github.com/vitejs/vite).
Followings are the packages that helped me _a lot_ for this project:

- [React Router v6](https://github.com/remix-run/react-router)
- [Jotai](https://github.com/pmndrs/jotai)
- [optic-ts](https://github.com/akheron/optics-ts)
- [@googlemaps/react-wrapper](https://github.com/googlemaps/react-wrapper)
- [Day.js](https://github.com/iamkun/dayjs/)
- [@tanstack/react-table](https://github.com/TanStack/table)

## Usage

### Note

- [Nodejs](https://nodejs.org/) needs to be installed in your system.
- I use [Yarn](https://yarnpkg.com/) package manager.

### Initalization

After cloning/forking, move into the project root, and change the **base name** with respect to **your repository name** (e.g., if your repo name is 'streetview_test', then rename it as '/streetview_test/') in **vite.config.ts**:

```ts
// vite.config.ts
...
export default defineConfig({
  // Base name for this GitHub repository
  // If you plan to fork this repo in your own repository,
  // Please change this base name w.r.t your repository name
  // E.g., repo name: 'streetview_exploration' -> base: '/streetview_exploration/'
  // Reference: https://github.com/metonym/vite-plugin-gh-pages
  base: '/streetview_test/', // 👈 Edit here
  plugins: [
    react({ babel: { plugins: [jotaiDebugLabel, jotaiReactRefresh] } }),
    tsconfigPaths(),
    ghPages(),
  ],
});
```

Then install dependencies using Yarn:

```bash
$ yarn
```

### Dev server

After some code changes, you can preview your work in the browser with the dev server in Vite:

```bash
$ yarn serve

VITE v3.1.4  ready in 1047 ms

➜  Local:   http://127.0.0.1:5173/streetview_exploration_demo/
➜  Network: use --host to expose
```

Visit the local address (i.e., http://127.0.0.1:5173/streetview_exploration_demo) in the browser. Note that HMR (hot module reloading) is on so you can immediately view the results in the browser after code changes.

### Build (and publish to GitHub Pages)

Thanks to [vite-plugin-gh-pages](https://github.com/metonym/vite-plugin-gh-pages), it **automatically publish** this project to the GitHub Pages for your repository after 'yarn build':

```bash
$ yarn build

yarn run v1.22.15
$ tsc && vite build
vite v3.1.4 building for production...
✓ 58 modules transformed.
dist/index.html                  1.02 KiB
dist/assets/index.23d77ae0.css   7.05 KiB / gzip: 2.13 KiB
dist/assets/index.7e54fd3a.js    386.70 KiB / gzip: 107.39 KiB
🎉 Published `dist` to branch `gh-pages`.
Done in 12.68s.
```

You can see the published app at https://[your-github-account].github.io/[this-repo-name].

If you do not want this behavior, then comment (or remove) lines related to vite-plugin-gh-pages in vite.config.js:

```ts
// vite.config.js
...
// Plug-in to publish GitHub Pages on 'yarn build'
// If you do not want to publish this application to the gh-page branch,
// Just remove this import and 'ghPages' object in 'plugins' array
// import { ghPages } from 'vite-plugin-gh-pages'; // 👈 Comment here

// https://vitejs.dev/config/
export default defineConfig({
  ...
  base: '/', // 👈 I am not sure, but I think you need to set the base as '/'.
  plugins: [
    react({ babel: { plugins: [jotaiDebugLabel, jotaiReactRefresh] } }),
    tsconfigPaths(),
    // ghPages(), // 👈 Comment here
  ],
});
```

Then 'yarn build' only build this project locally.

## miscellaneous

### Eslint, Prettier configurations

- [WONILLISM's Blog](https://wonillism.tistory.com/271)

### Favicon

- Downloaded from [favicon.io](https://favicon.io/emoji-favicons/world-map).
- Original emoji graphic from the open source project [Twemoji](https://twemoji.twitter.com/), copyright 2020 Twitter, Inc and other contributors. Licensed under [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/).
# BSPL
# BSPL
