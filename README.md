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
npm init svelte@next tip-jar
```

This script will work as a wizard, showing you a few questions to get started, so:

1. Select an Skeleton projeect
2. Will not use Typescript (unless you want, but the course will not showcase the use of TS)
3. Add ESLint
4. Add Prettier

After that you just need to enter into the newly created folder and install the dependencies

```bash
cd tip-jar
npm install
```

### TailwindCSS

As mentioned before, this project will use Tailwind to give the UI a little touch, to configure tailwind inside your svelteKit project, you can use a simple script named
[svelte-add](https://github.com/svelte-add/svelte-add)

```bash
npx svelte-add@latest tailwindcss
npm install
```

### Hardhat

[Hardhat](https://hardhat.org) is the development environment of choice for this course, it allows you to compile, deploy, test and debug your smart contract.
It helps you to run a local Ethereum network allowing you to have test accounts and to locally run your solidity code.

Let's install the required packages.

- Hardhat: The development environment
- Chai: The assertion library for testing the contract
- Ethers.js: A javascript library to interact with the Ethereum Blockchain
- hardhat-waffle: A plugin to work with Waffle, a tool to test smart contracts

```bash
npm install ethers hardhat @nomiclabs/hardhat-waffle ethereum-waffle chai @nomiclabs/hardhat-ethers
```

## Configuration

Now that you have all the dependencies ready to go, is time to do some configurations to be able to work.-

### Hardhat

First, run the started for hardhat

```bash
npx hardhat
```

This will ask if you want an example project or an empty hardhat configuration, choose "Create an empty hardhat.config.js"

After that, let's create some folders that you'll need

```bash
mkdir scripts
mkdri src/contracts
mkdir test
```

Now, let edit the hardhat configuration file to set the paths required

```javascript
require('@nomiclabs/hardhat-waffle'); // import the waffle plugin

/**
 * @type import('hardhat/config').HardhatUserConfig
 */
module.exports = {
	solidity: '0.8.4', // The version of solidity
	paths: {
		artifacts: './src/artifacts', // Where the compilation artifacts will live
		sources: './src/contracts' // Where the smart contract source code will found
	},
	networks: {
		// define the networks where hardhat will deploy
		hardhat: {
			chainId: 1337 // To be able to work with metamask in localhost
		}
	}
};
```

### SvelteKit

The svelteKit configuration will work out of the box, but if you want to deploy the web application to some place like Vercel, Cloudflare Workers, Netlify or similar you'll need [an adapter](https://kit.svelte.dev/docs#adapters)

Let's install the Vercel adapter to later in the course, deploy the web application there.

```bash
npm install --save-dev @sveltejs/adapter-vercel@next
```

And update the `svelte.config.js` to include the new adapter

```javascript
import preprocess from 'svelte-preprocess';
import adapter from '@sveltejs/adapter-vercel';

/** @type {import('@sveltejs/kit').Config} */
const config = {
	kit: {
		adapter: adapter(),
	},

	preprocess: [preprocess({})]
};

export default config;
```