# Ryan Way Website Start Project

This project is meant to be a template to quick start my current setup for website development in personal projects

## Quick Start (now lightweight and telemetry free)

```
npx degit ryan-way-boilerplate/sveltekit-daisyui
```

## From Scratch (If you're extra paranoid)

```bash
# sveltekit start
npm create svelte@latest

# tailwind
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p

# daisy ui
npm i -D daisyui@latest
```

### tailwind.config.js

```js
export default {
  content: ['./src/**/*.{html,js,svelte,ts}'],
  theme: {
    extend: {},
  },
  plugins: [require('daisyui')],
  daisyui: {
    themes: ['dark'],
  },
};
```

### ./src/app.css

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

### ./src/routes/+layout.svelte

```svelte
<script>
  import '../app.css';
</script>

<slot />
```

### ./src/routes/+page.svelte

```svelte
<h1 class="text-3xl font-bold underline">Hello world!</h1>

<style lang="postcss">
  :global(html) {
    background-color: theme(colors.gray.100);
  }
</style>
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://kit.svelte.dev/docs/adapters) for your target environment.
