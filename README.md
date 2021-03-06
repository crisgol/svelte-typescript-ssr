This repo was developed when Svelte 3 first came out. Since then better svelte-typescript integration has been developed, such as this [one](https://www.npmjs.com/package/svelte-preprocess)

=========

# Svelte + Typescript + Storybook SSR Boilerplate

This is a __Svelte + Typescript + Storybook SSR__ boiletplate project.
If you are intrested in developing only UI components or SPA, it is [here](https://github.com/farhan2106/svelte-typescript).

## Creating Pages / Routes

1. Create a `.html` file and a corresponding `.ts` file for the svelte component. During build time, the `.ts` will be combined with the `.html` file to become a svelte component. `.html` & `.ts` must have the same filename.

2. Subroutes is created by subfolder. It also assumes `/Index` as `/`. For example, `pages/member/Index.html` will create a route `http://localhost/member/`

3. Every page has its own client side javascript to be used during hydration. This client side JS will load the minimum required svelte component.

## How does the build process works?

1) Compile typescript and put it `build` folder,
2) Combine svelte html & svelte js (generated from typescript) together
3) Generated the list of entry files to be used by webpack for client side hydration
4) Profit!

## TODO

- Add service-worker
- Add Purify CSS
- Add Brotli compression
