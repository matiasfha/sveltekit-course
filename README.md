# 🎉 Welcome on board!

<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
<!-- ALL-CONTRIBUTORS-BADGE:END -->

## 🚌 Create your own SvelteKit Blog with MDsveX, Tailwind and Sanity

- [Demo app can be found here]()

Let's face it, every developer want to try new technologies, and what a better place to try it out that your own personal site or blog?

Is also a very well known fact that creating content is a very good way to: learn and to create a profile or portfolio for your self.

In this coures you'll learn how to start working with one of the coolest frameworks out there: [SvelteKit](https://kit.svelte.dev/), how to style your site with [TailwindCSS](https://tailwindcss.com/), how to handle your content with [Sanity](https://sanity.io) in combination with [github](https://github.com/) and your preferred host platform.


> **Important** 
> SvelteKit is still in beta. Expect bugs! Read more [here](https://svelte.dev/blog/sveltekit-beta), and track progress towards 1.0 [here](https://github.com/sveltejs/kit/issues?q=is%3Aopen+is%3Aissue+milestone%3A1.0+sort%3Aupdated-desc).
> This course was recorded pointing to the version 1.0.0-next.437 of Svelte kit 
> It will be updated after sveltekit reach version 1.0.0 

### What is SvelteKit

TLDR; It's a UI framework that compiles your components to highly optimized vanilla JavaScript

SvelteKit is Svelte's take on the web application framework. This is the new (still in beta) official way to develop applications with Svelte. It is packed with features like routing, layouts, stage management, API routes, SSG, and SSR. If you come from React or Vue world, SvelteKit is the counterpart of Nextjs or Nuxt.

SvelteKit helps you to make static sites, server-rendered sites, and even hybrid static/server-rendered apps. It delivers an outstanding developer experience and fast user experience like the Svelte philosophy describes.

In general words, SvelteKit is a tool to take your Svelte code and transform it into a node app or static files. You can consider Svelte as the underlying language and SvelteKit the set that brings the server-side and some options about how an application should be architected.


### What is MDX and MDsveX

[MDX](https://github.com/mdx-js/mdx) is a combination of Markdown and JSX

An authoring format that allows the writer to write the well-known markdown format but also introduce dynamic content by using the power of JSX components

It takes a string of markdown and transforms it to a Javascript string (React or Svelte)

It basically allows you to consider a regular markdown file as a component opening the door to add working code into the markdown file.

The MDX parser will insert your custom components into the parsed result, you can even replace base elements like paragraphs, headings, and others HTML elements.

This allows you to have a better authoring experience and to create all of your content using your lovely markdown, but also empowering your content with rich media elements like interactive charts, alerts, or embed external content like youtube videos, images, etc.

[MDsveX](https://mdsvex.com/) is the answer from [Svelte ](https://svelte.dev)world to the same need of authoring rich media content using a powerful media like markdown. This is a markdown pre-processor for Svelte components, this preprocessor allows you to use Svelte components in your markdown, or vice versa. It supports all Svelte syntax and almost all Markdown

It uses  [remark](https://remark.js.org/) and [rehype](https://github.com/rehypejs/rehype) so you can use several plugins to enhance your experience.


## 👨🏻‍💻 Course summary

Ok. Are you ready? Cool, this will be quite a journey but fun and full of challenges. A few this that you'll be able to learn.

- How to setup SvelteKit.
- How to setup MDsveX
- How to setup Tailwindcss
- How to use setup Sanity
- How to generate social images using cloudinary
- How to use Sanity webhook with Github API to automatically trigger a new build in your content
- How to use webhooks and 3rd party APIs to repost your content.
- How to test your site with playwright
- How to deploy your site

## 👨🏻‍💻 Who Am I?
<p align="center">
<img src="https://github.com/matiasfha.png" width="200" />
</p>

👋 I [Matías Hernández](https://matiashernandez.dev), father, developer, podcaster, writer and instructor.

I started my journey many years ago (even before jQuery became a thing), though this years I tried many different things but web developmet has always been my passion. During the last 10 years I officialy worked as "Softare Engineer" or "Developer" (the role name depends on the company 🤷‍♂️) for many different projects. During this years I collected ideas, concepts and knowledge that I try to share in different mediums to help other developers to level up their careers.

I love what I do and I try to bring the same passion to the content creation trough courses at [egghead.io](https://matiasfha.dev/egghead), articles en [FreeCodeCamp](https://matiasfha.dev/fcces), [my blog](https://matiashernandez.dev), [Cloudinary](https://mediajams.dev/author/matias-hernandez) and other publicationss and also with my podcasts [Café con Tech](https://www.cafecon.tech/) & [Control Remoto](https://www.controlremoto.io/) and finally thorugh my [newsletter](https://microbytes.dev).

Find me in twitter as [@matiasfha](https://twitter.com/matiasfha)

## ⏰ Before the course

The main requisits to start with sveltekit development is an "intermediate" knowledege on javascript and web development in general. You can bring everything you already know!

### 🛠 Requirements

This are the things you need to susccessfully go through this course

#### Sytem Requirements

- [git](https://git-scm.com/) v2.13 or above
- [NodeJS](https://nodejs.org/) `12 || 14 || 15 || 16`
- [npm](https://www.npmjs.com/) v6 or superior or [pnpm](https://pnpm.io/)

This tools need to be part of your system, you can check each version in the terminal

```shell
$ git --version
$ node --version
$ npm --version
```

#### Configuration

> If you like, you can fork this repository so you can store your progress.

- [ ] Clonse the repository

```shell
git clone https://github.com/matiasfha/sveltekit-course
```

- [ ] Install the dependencies

```shell
cd sveltekit-course.git
pnpm install
```

> this can take a few minutes

If you have any problem during this process, please [fille an issue](https://github.com/matiasfha/sveltekit-course/issues/new).

#### Execute the project

The `main` branch hold the final project ready to be tested, if you want to run locally to check what you'll build you can do it by

```shell
npm run start
```

This will:

- spawn a local ethereum network
- compile and locally deploy the smart contract
- Run the contract tests
- run the web application and open your browser

> Now you just need to import an account into metamask to test the application locally
> This will be shown through the course

### ❓ How to run each lesson

Each video lesson have a companion code that you'll be able to find in a corresponding branch named as `lesson-XX`.

You can navigate through the branches to review the resulting code to follow the video lesson.

## 📝 About the course

### Lessons structure

Each lesson will show you a little step towards the en goals. Also each lesson have it's own branch and it's own Readme file that will give you some resources and written content related with the video lesson.

#### List of lessons


## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!