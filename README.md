# Lesson 01: Setup

<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
<!-- ALL-CONTRIBUTORS-BADGE:END -->

## Initial Setup

To start this project, you need to run through an small amount of setup steps to get everything ready to work.

First, let's think about what is the outcome of this project: *A personal site or blog to showcase your content or developer portfolio*.
¿What will be showcase in the site?
Base on the general description of the outcome the site should be able to:
- Display articles/posts written for developers, meaning, it should include at least code highlight.
- Display other content related with a developer portfolio like projects.

Also, ideally your site should be easy to find and the content should be good looking and shareable. 

Based on all of that you can derive a base stack.

- SvelteKit as the base framework.
- TailwindCss for the UI.
- MDsveX to allow you to write your article/posts in markdown but at same time allowing you to use dynamic components.
- Sanity as CMS to handle any content of your site as your projects or other things you want to showcase.
- Cloudinary to handle the open graph images to make your content better looking when sharing and also SEO friendly.
> Optionally, you can add the use of third party APIs to allow you to repost your content or to handle everything in the CMS but keeping the markdown files.

### SvelteKit

The first step will be to setup Sveltekit. 
SvelteKit will give you the structure, conventions and convinience required to build a web application

To start you just need to open a terminal and run a couple of commands

```bash
npm init svelte@next my-portfolio
```

This script will work as a wizard, showing you a few questions to get started, so:

1. Select an Skeleton projeect
2. Will not use Typescript (unless you want, but the course will not showcase the use of TS)
3. Add ESLint
4. Add Prettier

After that you just need to enter into the newly created folder and install the dependencies

```bash
cd my-portfolio
npm install
```

### TailwindCSS

As mentioned before, this project will use Tailwind to give the UI a little touch, to configure tailwind inside your svelteKit project, you can use a simple script named
[svelte-add](https://github.com/svelte-add/svelte-add)

```bash
npx svelte-add@latest tailwindcss
npm install
```

### MDsveX

[MDsveX](https://mdsvex.com/docs) It's a markdown preprocessor for Svelte components. Is the Svelte take on MDX.
This preprocessor allows you to use Svelte components inside your markdown files (or viceversa). 

You can do things like this:

```html
<script>
	import { Chart } from "../components/Chart.svelte";
</script>

# Here’s a chart

The chart is rendered inside our MDsveX document.

<Chart />
```

Is based on common and battle tested APIs like [`unified`](https://unifiedjs.com/), [`remark`](https://github.com/remarkjs) and [`rehype`](https://github.com/rehypejs/rehype) allowing you to use any remark or rehype plugins available or write your own plugins to enhance your experience and content.

> In fact during the lessons you'll found a few little tricks with rehype/remark.

To install you'll again use `svelte-add` by just typing

```bash
npx svelte-add@latest mdsvex
```

and install the corresponding dependencies

This will create the required files including the main configuration file `mdsvex.config.js` ready to be used


> Quick tip, if you know what your are doing you can install all of the above in one line `npx create @svelte-add/kit@latest my-portfolio --with tailwindcss+mdsvex`
## Configuration

There is no more configuration to do!.

You can try out what comes out of the box by just typing

```bash
npm run dev --open
```

Let's use this time to review some SvelteKit's concepts that will be in use during the course.

### Project files

A typical SvelteKit project looks like this:
```
my-project/
├ src/
│ ├ lib/
│ │ └ [your lib files]
│ ├ params/
│ │ └ [your param matchers]
│ ├ routes/
│ │ └ [your routes]
│ ├ app.html
│ ├ error.html
│ └ hooks.js
├ static/
│ └ [your static assets]
├ tests/
│ └ [your tests]
├ package.json
├ svelte.config.js
├ tsconfig.json
└ vite.config.js
└ mdsvex.config.js
```

#### src
The `src` directory contains the meat of your project.

- `lib` contains your library code, which can be imported via the `$lib` alias, or packaged up for distribution using svelte-package
- `params` contains any param matchers your app needs
- `routes` contains the routes of your application
- `app.html` is your page template — an HTML document containing the following placeholders:
    - `%sveltekit.head%`— `<link>` and `<script>` elements needed by the app, plus any `<svelte:head>` content
    -  `%sveltekit.body%`— the markup for a rendered page. Typically this lives inside a `<div>` or other element, rather than directly inside `<body>`, to prevent bugs caused by browser extensions injecting elements that are then destroyed by the hydration process
    - `%sveltekit.assets%` — either paths.assets, if specified, or a relative path to `paths.base`
    - `%sveltekit.nonce% `— a CSP nonce for manually included links and scripts, if used
- `error.html` (optional) is the page that is rendered when everything else fails. It can contain the following placeholders:
    - `%sveltekit.status%` — the HTTP status
    - `%sveltekit.message%` — the error message
- `hooks.js` (optional) contains your application's hooks

You can use `.ts` files instead of `.js` files, if using TypeScript.

#### static
Any static assets that should be served as-is, like robots.txt or favicon.png, go in here.

#### tests
If you chose to add tests to your project during npm create svelte@latest, they will live in this directory.

#### package.json
Your package.json file must include ``@sveltejs/kit``, svelte and vite as devDependencies.

When you create a project with npm create svelte@latest, you'll also notice that package.json includes "type": "module". This means that .js files are interpreted as native JavaScript modules with import and export keywords. Legacy CommonJS files need a .cjs file extension.

#### svelte.config.js
This file contains your Svelte and SvelteKit configuration.

#### tsconfig.json
This file (or jsconfig.json, if you prefer type-checked .js files over .ts files) configures TypeScript, if you added typechecking during npm create svelte@latest. Since SvelteKit relies on certain configuration being set a specific way, it generates its own .svelte-kit/tsconfig.json file which your own config extends.

#### vite.config.js
A SvelteKit project is really just a Vite project that uses the @sveltejs/kit/vite plugin, along with any other Vite configuration.


### Routing

The main feature and convention of SvelteKit is that is have a filesystem-based router, meaning that the routes of your application are defined by the *directories* in your codebase

> This differs a bit of previous versions and also from other metaframeworks where the routing is based on files.

By default all the routes are served from `src/routes`, where `src/routes` is the main route, `src/root/folder` will create the `/folder` route.

You can also do dynamic routes by usin `[]` in the folder name like `src/routes/blog/[slug]` this can be used to dynamically load data that can be identified by the `[slug]` portion of the url.

*Each route directory contains at least one file identified by the `+` prefix*


#### +page 
There are 3 related `+page` files that defines the route
- `+page.svelte` that is an svelte component. This is the content that will be rendered in the browser. Here is where you write your client facing code.

- `+page.js` If your page required some data before it can be rendered, this is the place to write that logic, retrieve the data and pass it to the page. This can be done using the `load` function (more on this later). This function runs along with the page svelte component: In the server and in the browser,.

- `+page.server.js` If you need or want to write logic to retrieve data that only run on the server, this is the file where you write that. During the client navigation SvelteKit will execute this file in the server to load the data. It use the same `load` function but will only run in the server (fully backend).

#### +layout
As in any other metaframework there is a way to "persist" certain components during the navigation, or in other words sharing a "shell" of components among your routes, like a navigation bar, footer, main container, etc.

- `+layout.svelte` This file will hold the content of your layout that will be applied to every route under the folder where this file lives. Meaing that `src/routes/+layout.svelte` will be globally applied but `src/routes/contact/+layout.svelte` will be only applied to components under the  `contacts` route.

> Note: Layout are nested, so the global layout will wrap the contacts layout.

- `+layout.js` Similar to the pages files, a layout can `load` data. This javascript (or typescript file) define a `load` function that will run on SSR and client side navigation. All the data returned by this function will be available to all the child pages.

- `+layout.server.js` If your layout data needs are only server side, you can move the `load` function from `+layout.js` to this file.


#### +server

Finally, the standalone api endpoint. You can define a route that will only have a file named `+server.js` this will define an "API endpoint" where you are in full control over the response.
This file can export a function corresponding to each of the HTTP verbs `GET`,`POST`,`PATCH`,`PUT`and `DELETE` allowing you to create a full api.



Now, its time to start creating your portfolio.