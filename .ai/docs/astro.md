### Install and Configure `@astrojs/sitemap` Integration

Source: https://v6.docs.astro.build/en/guides/integrations-guide

This example demonstrates the manual installation process for the `@astrojs/sitemap` integration. It involves installing the package via npm, pnpm, or yarn, and then importing and adding it to the `integrations` array in `astro.config.mjs`.

```bash
npm install @astrojs/sitemap

```

```bash
pnpm add @astrojs/sitemap

```

```bash
yarn add @astrojs/sitemap

```

```javascript
import { defineConfig } from 'astro/config';
import sitemap from '@astrojs/sitemap';


export default defineConfig({
  // ...
  integrations: [sitemap()],
  // ...
});

```

--------------------------------

### Implement start Function for Self-Hosted Servers (JavaScript)

Source: https://v6.docs.astro.build/en/reference/adapter-reference

The `start` function is exported when a host expects the server to be started manually, such as by listening on a port. This example shows setting up a fetch event listener.

```javascript
import { App } from 'astro/app';


export function start(manifest) {
  const app = new App(manifest);


  addEventListener('fetch', event => {
    // ...
  });
}
```

--------------------------------

### Create New Astro Project with pnpm

Source: https://v6.docs.astro.build/en/install-and-setup

This command initiates the Astro project creation wizard using pnpm. It guides the user through the setup process for a new Astro project.

```bash
pnpm create astro@latest
```

--------------------------------

### Create Astro Project from Official Example (Yarn)

Source: https://v6.docs.astro.build/en/install-and-setup

This command creates a new Astro project from an official example template using Yarn. The `--template` flag is used to specify the example.

```bash
yarn create astro --template <example-name>
```

--------------------------------

### Install @astrojs/netlify Adapter with npm, pnpm, or Yarn

Source: https://v6.docs.astro.build/en/guides/integrations-guide/netlify

Automates the setup of the Netlify adapter by installing the package and modifying the Astro configuration file.

```bash
npx astro add netlify

```

```bash
pnpm astro add netlify

```

```bash
yarn astro add netlify

```

--------------------------------

### Create Astro Project from Official Example (npm)

Source: https://v6.docs.astro.build/en/install-and-setup

This command creates a new Astro project using an official example template specified by `<example-name>`. It uses npm as the package manager.

```bash
npm create astro@latest -- --template <example-name>
```

--------------------------------

### Create New Astro Project with Yarn

Source: https://v6.docs.astro.build/en/install-and-setup

This command initiates the Astro project creation wizard using Yarn. It allows users to start a new Astro project with interactive setup.

```bash
yarn create astro
```

--------------------------------

### Create Astro Project from Official Example (pnpm)

Source: https://v6.docs.astro.build/en/install-and-setup

This command creates a new Astro project from an official example template using pnpm. Specify the template name with the `--template` flag.

```bash
pnpm create astro@latest --template <example-name>
```

--------------------------------

### Create New Astro Project with npm, pnpm, or Yarn

Source: https://v6.docs.astro.build/en/tutorial/1-setup/2

Use the `create astro` command with your preferred package manager (npm, pnpm, or Yarn) to initialize a new Astro project. This command triggers a setup wizard to guide you through project creation and dependency installation.

```bash
# create a new project with npm
npm create astro@latest
```

```bash
# create a new project with pnpm
pnpm create astro@latest
```

```bash
# create a new project with yarn
yarn create astro
```

--------------------------------

### Install @astrojs/solid-js Integration

Source: https://v6.docs.astro.build/en/guides/integrations-guide/solid-js

Automates the setup of the @astrojs/solid-js integration using the Astro CLI. This command prompts the user to confirm the installation.

```bash
npx astro add solid
```

```bash
pnpm astro add solid
```

```bash
yarn astro add solid
```

--------------------------------

### Install LibSQL Client for Astro

Source: https://v6.docs.astro.build/en/guides/backend/turso

Install the @libsql/client package using npm, pnpm, or Yarn to enable Turso connectivity within your Astro project.

```bash
npm install @libsql/client
```

```bash
pnpm add @libsql/client
```

```bash
yarn add @libsql/client
```

--------------------------------

### start()

Source: https://v6.docs.astro.build/en/reference/adapter-reference

An exported function that takes an SSR manifest and adapter arguments, used to start the server or listen for requests.

```APIDOC
## `start()`

### Description
An exported function that takes an SSR manifest as its first argument and an object containing your adapter `args` as its second argument. Some hosts expect you to _start_ the server yourselves, for example, by listening to a port.

### Method
`start(manifest: SSRManifest, options: any) => Record<string, any>`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
import { App } from 'astro/app';

export function start(manifest) {
  const app = new App(manifest);

  addEventListener('fetch', event => {
    // ...
  });
}
```

### Response
#### Success Response (200)
This function does not return a value, but initiates server-side operations.

#### Response Example
None
```

--------------------------------

### astro:server:setup Hook

Source: https://v6.docs.astro.build/en/reference/integrations-reference

The `astro:server:setup` hook runs after the server is configured but before it starts listening. It's suitable for adding middleware or modifying server behavior.

```APIDOC
## astro:server:setup

### Description
This hook runs after the server is configured and is a good place to add middleware or intercept requests.

### Method
`'astro:server:setup'?: (options: { server: ViteDevServer; refreshContent: (options: { loaders?: Array<string>; context?: Record<string, any>; }) => Promise<void>; }) => void | Promise<void>;`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
// Example usage within an integration
{ 
  name: 'my-integration',
  hooks: {
    'astro:server:setup': async ({ server, refreshContent }) => {
      server.middlewares.use('/_refresh', async (req, res) => {
        // ... middleware logic ...
        await refreshContent({ loaders: ['my-loader'] });
        // ... response logic ...
      });
    }
  }
}
```

### Response
#### Success Response (200)
None

#### Response Example
None
```

--------------------------------

### Run Astro Development Server

Source: https://v6.docs.astro.build/en/guides/cms/keystatic

Start Astro's development server to launch the Keystatic Admin UI dashboard. Access the dashboard at `http://127.0.0.1:4321/keystatic`.

```bash
npm run dev
```

--------------------------------

### Install Astro Integrations and Keystatic Packages

Source: https://v6.docs.astro.build/en/guides/cms/keystatic

Add the React and Markdoc integrations to your Astro project using the `astro add` command. Then, install the core Keystatic packages.

```bash
npx astro add react markdoc
```

```bash
pnpm astro add react markdoc
```

```bash
yarn astro add react markdoc
```

```bash
npm install @keystatic/core @keystatic/astro
```

```bash
pnpm add @keystatic/core @keystatic/astro
```

```bash
yarn add @keystatic/core @keystatic/astro
```

--------------------------------

### Example Keystatic Post Frontmatter

Source: https://v6.docs.astro.build/en/guides/cms/keystatic

This is an example of the frontmatter generated for a Keystatic post. It includes metadata like the title, which is used by Astro for rendering.

```markdown
---
title: My First Post
---


This is my very first post. I am **super** excited!

```

--------------------------------

### Install Cloudflare Adapter with npm

Source: https://v6.docs.astro.build/en/guides/integrations-guide/cloudflare

Installs the @astrojs/cloudflare adapter using npm. This command automates the setup process by adding the necessary package and configuring your astro.config.mjs file.

```bash
npx astro add cloudflare
```

--------------------------------

### Migrate Markdown to MDX Example

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

Shows an example of frontmatter and component import for migrating an Astro Markdown file to MDX format, requiring the `@astrojs/mdx` integration.

```astro
---
layout: '../../layouts/BaseLayout.astro'
// setup: |  // Removed in v2.0
//  import ReactCounter from '../../components/ReactCounter.jsx'
title: 'Migrating to MDX'
date: 2022-07-26
tags: ["markdown", "mdx", "astro"]
---
import ReactCounter from '../../components/ReactCounter.jsx'

```

--------------------------------

### Install Astro Integrations and Frameworks (npm)

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

Commands to install new Astro integrations and their corresponding frameworks using npm. This replaces the previous renderer system.

```bash
# Install your new integrations and frameworks:
# (Read the full walkthrough: https://docs.astro.build/en/guides/integrations-guide)
npm install @astrojs/lit lit
npm install @astrojs/react react react-dom
```

--------------------------------

### Create Astro Blog Project with npm

Source: https://v6.docs.astro.build/en/guides/migrate-to-astro/from-eleventy

This command initializes a new Astro project using the 'blog' template with npm. It's a straightforward way to start a blog with Astro.

```bash
npm create astro@latest -- --template blog
```

--------------------------------

### Install NightwatchJS in Astro Project

Source: https://v6.docs.astro.build/en/guides/testing

Install NightwatchJS using npm, pnpm, or Yarn. This command initializes NightwatchJS within your Astro project, guiding you through setup options like language choice, test folder naming, and component/mobile testing.

```bash
npm init nightwatch@latest
```

```bash
pnpm create nightwatch
```

```bash
yarn create nightwatch
```

--------------------------------

### Install Cloudflare Adapter with Yarn

Source: https://v6.docs.astro.build/en/guides/integrations-guide/cloudflare

Installs the @astrojs/cloudflare adapter using Yarn. This command automates the setup process by adding the necessary package and configuring your astro.config.mjs file.

```bash
yarn astro add cloudflare
```

--------------------------------

### Install Astro Project Dependencies with Bun

Source: https://v6.docs.astro.build/en/recipes/bun

Installs project dependencies using Bun. This command should be run after creating a new Astro project, especially if dependencies were skipped during setup.

```bash
bun install
```

--------------------------------

### Install Cloudflare Adapter with pnpm

Source: https://v6.docs.astro.build/en/guides/integrations-guide/cloudflare

Installs the @astrojs/cloudflare adapter using pnpm. This command automates the setup process by adding the necessary package and configuring your astro.config.mjs file.

```bash
pnpm astro add cloudflare
```

--------------------------------

### Install ButterCMS SDK for Astro (npm, pnpm, Yarn)

Source: https://v6.docs.astro.build/en/guides/cms/buttercms

Demonstrates how to install the ButterCMS SDK as a project dependency using different package managers.

```bash
npm install buttercms
```

```bash
pnpm add buttercms
```

```bash
yarn add buttercms
```

--------------------------------

### Create Project Directory and Navigate

Source: https://v6.docs.astro.build/en/install-and-setup

Creates a new directory for your Astro project and navigates into it using standard shell commands.

```bash
mkdir my-astro-project
cd my-astro-project
```

--------------------------------

### Install @astrojs/react using npm, pnpm, or Yarn

Source: https://v6.docs.astro.build/en/guides/integrations-guide/react

Automates the setup of the @astrojs/react integration. Choose your preferred package manager to run the command.

```bash
npx astro add react
```

```bash
pnpm astro add react
```

```bash
yarn astro add react
```

--------------------------------

### Install Prettier and Astro Plugin (Yarn)

Source: https://v6.docs.astro.build/en/editor-setup

Installs Prettier and the official Astro Prettier plugin using Yarn. This setup allows for consistent code formatting across your Astro project.

```bash
yarn add --dev --exact prettier prettier-plugin-astro
```

--------------------------------

### Install Zerops CLI (Shell)

Source: https://v6.docs.astro.build/en/guides/deploy/zerops

Provides instructions for installing the Zerops CLI (zcli) by downloading the binary directly. This is the first step to triggering the pipeline locally.

```shell
# To download the zcli binary directly,

```

--------------------------------

### Configure Astro with Vite (v0.21+)

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

Starting with Astro v0.21, the build process is powered by Vite. Migrate configurations from `snowpack.config.mjs` to `astro.config.mjs`. This example shows a basic Astro configuration with Vite integration.

```javascript
// @ts-check


/** @type {import('astro').AstroUserConfig} */
export default {
  renderers: [],
  vite: {
    plugins: [],
  },
};
```

--------------------------------

### Start Astro Development Server using npm, pnpm, or Yarn

Source: https://v6.docs.astro.build/en/develop-and-build

These commands start the Astro development server, which provides a live preview of your website as you make code changes. Ensure you are in your project directory before running these commands. The server typically runs on http://localhost:4321/.

```bash
npm run dev
```

```bash
pnpm run dev
```

```bash
yarn run dev
```

--------------------------------

### astro:build:setup Hook

Source: https://v6.docs.astro.build/en/reference/integrations-reference

The `astro:build:setup` hook runs immediately before the build starts, after the Vite config is finalized. It provides the final chance to modify the Vite config.

```APIDOC
## astro:build:setup

### Description
Runs after the `astro:build:start` hook and immediately before the build. The Vite config is completely constructed at this point, offering the final chance to modify it. Useful for overwriting defaults or making final adjustments. Prefer `astro:build:start` if unsure.

### Method
`'astro:build:setup'?: (options: { vite: vite.InlineConfig; pages: Map<string, PageBuildData>; updateConfig: (newConfig: vite.InlineConfig) => void; logger: AstroIntegrationLogger; }) => void | Promise<void>;`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
// Example usage within an integration
import type vite from 'vite';

{
  name: 'my-integration',
  hooks: {
    'astro:build:setup': async ({ vite: viteConfig, pages, updateConfig, logger }) => {
      logger.info('Setting up build configuration...');
      // Example: Modify Vite config
      updateConfig({
        plugins: [...(viteConfig.plugins || []), myCustomPlugin()]
      });
    }
  }
}
```

### Response
#### Success Response (200)
None

#### Response Example
None
```

--------------------------------

### Manually Configure Integrations in `astro.config.mjs`

Source: https://v6.docs.astro.build/en/guides/integrations-guide

Integrations are added to your Astro project via the `integrations` property in `astro.config.mjs`. This example shows importing and using an installed npm package integration, a local integration file, and an inline integration object.

```javascript
import { defineConfig } from 'astro/config';
import installedIntegration from '@astrojs/vue';
import localIntegration from './my-integration.js';


export default defineConfig({
  integrations: [
    // 1. Imported from an installed npm package
    installedIntegration(),
    // 2. Imported from a local JS file
    localIntegration(),
    // 3. An inline object
    {name: 'namespace:id', hooks: { /* ... */ }},
  ]
});

```

--------------------------------

### Add Integrations Automatically with `astro add`

Source: https://v6.docs.astro.build/en/guides/integrations-guide

Automate the setup of official and some community Astro integrations using the `astro add` command. This command updates your configuration file and installs necessary dependencies. It supports adding multiple integrations at once.

```bash
npx astro add react

```

```bash
pnpm astro add react

```

```bash
yarn astro add react

```

```bash
npx astro add react sitemap partytown

```

```bash
pnpm astro add react sitemap partytown

```

```bash
yarn astro add react sitemap partytown

```

--------------------------------

### Specify Preview Entrypoint for Server Startup

Source: https://v6.docs.astro.build/en/reference/adapter-reference

Defines the path or ID of a module responsible for starting the built server when `astro preview` is run. This allows customization of the server startup process for previewing.

```javascript
export default function createIntegration() {
  return {
    name: '@example/my-adapter',
    hooks: {
      'astro:config:done': ({ config, setAdapter }) => {
        setAdapter({
          name: '@example/my-adapter',
          serverEntrypoint: '@example/my-adapter/server.js',
          previewEntrypoint: '@example/my-adapter/preview.js',
        });
      },
    },
  };
}
```

--------------------------------

### Create Astro Adapter with Build-Time Arguments

Source: https://v6.docs.astro.build/en/reference/adapter-reference

This example shows how to create an Astro adapter and pass build-time arguments to its server entrypoint. The `args` property is used to include configuration details, such as the location of Astro-generated assets, which can be accessed at runtime.

```javascript
export default function createIntegration() {
  return {
    name: '@example/my-adapter',
    hooks: {
      'astro:config:done': ({ config, setAdapter }) => {
        setAdapter({
          name: '@example/my-adapter',
          serverEntrypoint: '@example/my-adapter/server.js',
          args: {
            assets: config.build.assets
          }
        });
      },
    },
  };
}
```

--------------------------------

### Install Deno Deploy CLI

Source: https://v6.docs.astro.build/en/guides/deploy/deno

Installs the Deno Deploy CLI globally and with necessary flags for safe and forceful installation.

```bash
deno install -gArf jsr:@deno/deployctl
```

--------------------------------

### Configure Vite Plugins in Astro (v0.21+)

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

Vite plugins can be configured within `astro.config.mjs` starting from Astro v0.21. This example demonstrates how to include the `vite-imagetools` plugin.

```javascript
import { imagetools } from 'vite-imagetools';


export default {
  vite: {
    plugins: [imagetools()],
  },
};
```

--------------------------------

### Manually Install @astrojs/netlify Adapter

Source: https://v6.docs.astro.build/en/guides/integrations-guide/netlify

Installs the Netlify adapter as a project dependency using a package manager and configures it in `astro.config.mjs`.

```bash
npm install @astrojs/netlify

```

```bash
pnpm add @astrojs/netlify

```

```bash
yarn add @astrojs/netlify

```

```javascript
import { defineConfig } from 'astro/config';
import netlify from '@astrojs/netlify';


export default defineConfig({
   // ...
   adapter: netlify(),
});

```

--------------------------------

### Create First Astro Page (index.astro)

Source: https://v6.docs.astro.build/en/install-and-setup

Creates the initial Astro page located at src/pages/index.astro. Includes component frontmatter and a basic HTML template with styling.

```astro
---
// Welcome to Astro! Everything between these triple-dash code fences
// is your "component frontmatter". It never runs in the browser.
console.log('This runs in your terminal, not the browser!');
---
<!-- Below is your "component template." It's just HTML, but with
    some magic sprinkled in to help you build great templates. -->
<html>
  <body>
    <h1>Hello, World!</h1>
  </body>
</html>
<style>
  h1 {
    color: orange;
  }
</style>
```

--------------------------------

### Install Juno CLI

Source: https://v6.docs.astro.build/en/guides/deploy/juno

These commands show how to install the Juno CLI globally using different package managers. The CLI is used for authenticating with Juno and deploying your site.

```bash
npm i -g @junobuild/cli
```

```bash
pnpm add -g @junobuild/cli
```

```bash
yarn global add @junobuild/cli
```

--------------------------------

### Install Netlify CLI Globally (npm, pnpm, Yarn)

Source: https://v6.docs.astro.build/en/guides/deploy

Instructions for globally installing the Netlify CLI using npm, pnpm, and Yarn package managers. This CLI is used for deploying sites to Netlify.

```bash
npm install --global netlify-cli
```

```bash
pnpm add --global netlify-cli
```

```bash
yarn global add netlify-cli
```

--------------------------------

### Start Local Preview Server with Astro

Source: https://v6.docs.astro.build/en/reference/programmatic-reference

Starts a local server to serve your Astro build output. The server behavior depends on whether an adapter is configured. If no adapter is set, it serves static files; otherwise, the adapter provides the server. Adapters may not always provide a preview server.

```javascript
import { preview } from "astro";


const previewServer = await preview({
  root: "./my-project",
});


// Stop the server if needed
await previewServer.stop();
```

--------------------------------

### Install Prisma Dependencies and Initialize

Source: https://v6.docs.astro.build/en/guides/backend/prisma-postgres

Installs necessary Prisma packages and initializes Prisma in your Astro project. This sets up the Prisma directory and environment variables for database connection.

```bash
npm install prisma tsx --save-dev
npm install @prisma/adapter-pg @prisma/client
npx prisma init --db --output ./generated
```

--------------------------------

### Create Astro Project with Blog Template

Source: https://v6.docs.astro.build/en/guides/migrate-to-astro/from-gridsome

This command initiates a new Astro project using the official blog starter template. It's a common starting point for migrating Gridsome blogs to Astro.

```bash
npm create astro@latest -- --template blog
```

```bash
pnpm create astro@latest --template blog
```

```bash
yarn create astro --template blog
```

--------------------------------

### astro:build:start Hook

Source: https://v6.docs.astro.build/en/reference/integrations-reference

The `astro:build:start` hook runs after configuration is done but before the production build begins, allowing setup of global objects or clients needed for the build.

```APIDOC
## astro:build:start

### Description
Runs after the `astro:config:done` event, but before the production build begins. Use this to set up any global objects or clients needed during a production build, or to extend adapter API build configuration options.

### Method
`'astro:build:start'?: (options: { logger: AstroIntegrationLogger; }) => void | Promise<void>;`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
// Example usage within an integration
{
  name: 'my-integration',
  hooks: {
    'astro:build:start': async ({ logger }) => {
      logger.info('Starting production build...');
    }
  }
}
```

### Response
#### Success Response (200)
None

#### Response Example
None
```

--------------------------------

### Create robots.txt for Static Assets

Source: https://v6.docs.astro.build/en/install-and-setup

Creates a robots.txt file in the public/ directory to instruct search engine bots on how to crawl and index the site.

```text
# Example: Allow all bots to scan and index your site.
# Full syntax: https://developers.google.com/search/docs/advanced/robots/create-robots-txt
User-agent: *
Allow: /
```

--------------------------------

### Manually Install @astrojs/db Package

Source: https://v6.docs.astro.build/en/guides/integrations-guide/db

Installs the @astrojs/db package manually using a package manager. This is an alternative to the `astro add` command for users who prefer manual setup.

```bash
npm install @astrojs/db
```

```bash
pnpm add @astrojs/db
```

```bash
yarn add @astrojs/db
```

--------------------------------

### Install Project Dependencies (npm)

Source: https://v6.docs.astro.build/en/guides/deploy/deno

Installs all project dependencies listed in `package.json` using npm. This is a standard step before building or running an Astro project.

```bash
npm install
```

--------------------------------

### Astro Build Setup Hook

Source: https://v6.docs.astro.build/en/reference/integrations-reference

The `astro:build:setup` hook executes after `astro:build:start` and just before the build begins. At this stage, the Vite configuration is finalized, offering a last opportunity to modify it. It provides access to the Vite configuration, page data, a function to update the config, and a logger.

```typescript
'astro:build:setup'?: (options: {
  vite: vite.InlineConfig;
  pages: Map<string, PageBuildData>;
  updateConfig: (newConfig: vite.InlineConfig) => void;
  logger: AstroIntegrationLogger;
}) => void | Promise<void>;
```

--------------------------------

### Install Decap CMS via pnpm

Source: https://v6.docs.astro.build/en/guides/cms/decap-cms

Installs the Decap CMS application package using pnpm. This is an alternative package manager installation method for Astro projects.

```bash
pnpm add decap-cms-app
```

--------------------------------

### Create Keystatic Configuration File

Source: https://v6.docs.astro.build/en/guides/cms/keystatic

Define your content schema and storage configuration in `keystatic.config.ts`. This example sets up local storage and a 'posts' collection with title and content fields.

```typescript
import { config, fields, collection } from '@keystatic/core';


export default config({
  storage: {
    kind: 'local',
  },


  collections: {
    posts: collection({
      label: 'Posts',
      slugField: 'title',
      path: 'src/content/posts/*',
      format: { contentField: 'content' },
      schema: {
        title: fields.slug({ name: { label: 'Title' } }),
        content: fields.markdoc({
          label: 'Content',
        }),
      },
    }),
  },
});
```

--------------------------------

### Install Sass Dependency for Astro

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

If your Astro project uses Sass, you need to install it as a development dependency. This is because Sass is now an optional dependency to reduce the initial npm install size.

```bash
npm install sass --save-dev
```

--------------------------------

### Install Zerops CLI

Source: https://v6.docs.astro.build/en/guides/deploy/zerops

Installs the Zerops CLI globally using npm. This command requires Node.js and npm to be installed on your system.

```bash
npm i -g @zerops/zcli
```

--------------------------------

### Create New Astro Project with npm

Source: https://v6.docs.astro.build/en/getting-started

This command initiates the creation of a new Astro project using npm. It utilizes the Astro CLI to guide the user through the project setup process. No specific dependencies are required beyond Node.js and npm.

```bash
npm create astro@latest
```

--------------------------------

### Install Ghost Content API Client (npm)

Source: https://v6.docs.astro.build/en/guides/cms/ghost

Install the official Ghost Content API client package using npm. This package allows your Astro project to interact with your Ghost site's data.

```bash
npm install @tryghost/content-api
npm install --save @types/tryghost__content-api
```

--------------------------------

### Install @astrojs/mdx Integration

Source: https://v6.docs.astro.build/en/guides/integrations-guide/mdx

Automate the setup of the @astrojs/mdx integration using the Astro CLI. This command adds the necessary configuration to your project. Alternatively, manual installation involves adding the package and configuring it in `astro.config.js`.

```bash
npx astro add mdx
```

```bash
pnpm astro add mdx
```

```bash
yarn astro add mdx
```

--------------------------------

### Install Prism for Astro

Source: https://v6.docs.astro.build/en/guides/syntax-highlighting

Provides instructions for installing the `@astrojs/prism` package, which is necessary for using the `<Prism />` component for syntax highlighting. It includes commands for npm, pnpm, and Yarn.

```bash
npm install @astrojs/prism

```

```bash
pnpm add @astrojs/prism

```

```bash
yarn add @astrojs/prism

```

--------------------------------

### Add Start Script to package.json

Source: https://v6.docs.astro.build/en/guides/deploy/seenode

Updates the `package.json` file to include a 'start' script. This script is used to run the built Astro server in production mode, essential for deployment.

```json
{
  "scripts": {
    "dev": "astro dev",
    "build": "astro build",
    "preview": "astro preview",
    "start": "NODE_ENV=production node ./dist/server/entry.mjs"
  }
}
```

--------------------------------

### Initialize Azion Project

Source: https://v6.docs.astro.build/en/guides/deploy/azion

Initializes and configures your project for deployment with Azion. This command sets up the necessary configuration files and structure for your application on the Azion platform.

```bash
azion init
```

--------------------------------

### Install @astrojs/markdoc with npm, pnpm, or Yarn

Source: https://v6.docs.astro.build/en/guides/integrations-guide/markdoc

Automate the setup of the @astrojs/markdoc integration using the Astro CLI. This command adds the necessary configuration to your project.

```bash
npx astro add markdoc

```

```bash
pnpm astro add markdoc

```

```bash
yarn astro add markdoc

```

--------------------------------

### Install Project Dependencies (Yarn)

Source: https://v6.docs.astro.build/en/guides/deploy/deno

Installs all project dependencies listed in `package.json` using Yarn. This is a standard step before building or running an Astro project.

```bash
yarn
```

--------------------------------

### Serve Static Astro Site with Deno

Source: https://v6.docs.astro.build/en/guides/deploy/deno

Starts a static file server using Deno to serve the contents of the `dist` directory. This is used for deploying static Astro sites.

```bash
deno run -A jsr:@std/http/file-server dist
```

--------------------------------

### Install Project Dependencies (pnpm)

Source: https://v6.docs.astro.build/en/guides/deploy/deno

Installs all project dependencies listed in `package.json` using pnpm. This is a standard step before building or running an Astro project.

```bash
pnpm install
```

--------------------------------

### Run Astro Development Server with Bun

Source: https://v6.docs.astro.build/en/recipes/bun

Starts the Astro development server using Bun. This command enables live reloading and other development-specific features for local testing.

```bash
bun run dev
```

--------------------------------

### Install Supabase Client Library

Source: https://v6.docs.astro.build/en/guides/backend/supabase

Install the official Supabase JavaScript client library, `@supabase/supabase-js`, into your Astro project. This library provides the necessary tools to interact with your Supabase backend.

```bash
npm install @supabase/supabase-js
```

```bash
pnpm add @supabase/supabase-js
```

```bash
yarn add @supabase/supabase-js
```

--------------------------------

### Create Astro Blog Project with pnpm

Source: https://v6.docs.astro.build/en/guides/migrate-to-astro/from-eleventy

This command initializes a new Astro project using the 'blog' template with pnpm. It's an alternative to npm for package management.

```bash
pnpm create astro@latest --template blog
```

--------------------------------

### Install Tailwind Typography with Yarn

Source: https://v6.docs.astro.build/en/recipes/tailwind-rendered-markdown

Installs the `@tailwindcss/typography` package as a development dependency using Yarn. This step is required before configuring the plugin in your Tailwind setup.

```bash
yarn add --dev @tailwindcss/typography
```

--------------------------------

### Install @astrojs/preact Integration

Source: https://v6.docs.astro.build/en/guides/integrations-guide/preact

Automates the setup of the @astrojs/preact integration using the Astro CLI. This command simplifies the process of adding Preact support to your Astro project.

```bash
npx astro add preact

```

```bash
pnpm astro add preact

```

```bash
yarn astro add preact

```

--------------------------------

### Install Cosmic JS SDK with npm, pnpm, or Yarn

Source: https://v6.docs.astro.build/en/guides/cms/cosmic

Installs the Cosmic JavaScript SDK, which is necessary for fetching data from your Cosmic bucket. This command can be executed using npm, pnpm, or Yarn.

```bash
npm install @cosmicjs/sdk
```

```bash
pnpm add @cosmicjs/sdk
```

```bash
yarn add @cosmicjs/sdk
```

--------------------------------

### Install Missing Integration Dependencies

Source: https://v6.docs.astro.build/en/guides/integrations-guide

If you encounter 'Cannot find package' warnings after adding an integration, it may be due to missing peer dependencies. Run the appropriate command for your package manager to install these missing packages.

```bash
npm install [package-name]

```

```bash
pnpm add [package-name]

```

```bash
yarn add [package-name]

```

--------------------------------

### Install Deno Astro Adapter (npm)

Source: https://v6.docs.astro.build/en/guides/deploy/deno

Installs the `@deno/astro-adapter` package using npm. This is a prerequisite for enabling on-demand rendering with Deno in an Astro project.

```bash
npm install @deno/astro-adapter
```

--------------------------------

### Create Astro Project with Starlight Template

Source: https://v6.docs.astro.build/en/guides/migrate-to-astro/from-docusaurus

These commands demonstrate how to initialize a new Astro project using the official Starlight documentation theme. This is the recommended starting point for migrating from Docusaurus. The commands are provided for npm, pnpm, and Yarn package managers.

```bash
npm create astro@latest -- --template starlight
```

```bash
pnpm create astro@latest --template starlight
```

```bash
yarn create astro --template starlight
```

--------------------------------

### Create Astro Project from Template with Bun

Source: https://v6.docs.astro.build/en/recipes/bun

Creates a new Astro project using a specified template, either an official example or a GitHub repository. This allows for quick project bootstrapping with pre-defined configurations.

```bash
# create a new project with an official example
bun create astro@latest --template <example-name>
# create a new project based on a GitHub repository’s main branch
bun create astro@latest --template <github-username>/<github-repo>
```

--------------------------------

### Start Astro Development Server with npm, pnpm, or Yarn

Source: https://v6.docs.astro.build/en/reference/cli-reference

Starts the Astro development server, providing a live preview of your site. This command is essential for the development workflow. It can be executed using npm, pnpm, or Yarn.

```bash
# start the development server
npx astro dev
```

```bash
# start the development server
pnpm astro dev
```

```bash
# start the development server
yarn astro dev
```

--------------------------------

### Enable Astro Add Installation via package.json (JSON)

Source: https://v6.docs.astro.build/en/reference/adapter-reference

Shows how to configure a package.json file to allow an Astro adapter to be installed using the `astro add` command. By adding `astro-adapter` to the `keywords` array, users can easily discover and add the adapter to their projects.

```json
{
  "name": "example",
  "keywords": ["astro-adapter"],
}
```

--------------------------------

### Preview Server API

Source: https://v6.docs.astro.build/en/reference/programmatic-reference

Starts a local server to serve your build output. The preview server functionality may vary depending on the adapter configuration.

```APIDOC
## `preview()`

### Description
Similar to `astro preview`, it starts a local server to serve your build output. If no adapter is set in the configuration, the preview server will only serve the built static files. If an adapter is set in the configuration, the preview server is provided by the adapter. Adapters are not required to provide a preview server, so this feature may not be available depending on your adapter of choice.

### Method
`preview(inlineConfig: AstroInlineConfig) => Promise<PreviewServer>`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
`inlineConfig` (AstroInlineConfig) - Configuration object for the preview server.

### Request Example
```javascript
import { preview } from "astro";


const previewServer = await preview({
  root: "./my-project",
});


// Stop the server if needed
await previewServer.stop();
```

### Response
#### Success Response (200)
`PreviewServer` - An object representing the preview server with methods to control and query its status.

#### `PreviewServer` Interface
```typescript
export interface PreviewServer {
  host?: string;
  port: number;
  closed(): Promise<void>;
  stop(): Promise<void>;
}
```

#### Response Example
```json
{
  "host": "localhost",
  "port": 4321
}
```

### `stop()` Method
#### Description
Asks the preview server to close, stop accepting requests, and drop idle connections. The returned `Promise` resolves when the close request has been sent. This does not mean that the server has closed yet. Use the `closed()` method if you need to ensure the server has fully closed.

#### Method
`stop(): Promise<void>`

### `closed()` Method
#### Description
Returns a `Promise` that will resolve once the server is closed and reject if an error happens on the server.

#### Method
`closed(): Promise<void>`
```

--------------------------------

### Run ApostropheCMS Development Server

Source: https://v6.docs.astro.build/en/guides/cms/apostrophecms

Command to start the local ApostropheCMS development server. Requires the `APOS_EXTERNAL_FRONT_KEY` environment variable to be set.

```bash
APOS_EXTERNAL_FRONT_KEY='MyRandomString' npm run dev
```

--------------------------------

### Install Ghost Content API Client (pnpm)

Source: https://v6.docs.astro.build/en/guides/cms/ghost

Install the official Ghost Content API client package using pnpm. This package allows your Astro project to interact with your Ghost site's data.

```bash
pnpm add @tryghost/content-api
pnpm add --save-dev @types/tryghost__content-api
```

--------------------------------

### Install Ghost Content API Client (Yarn)

Source: https://v6.docs.astro.build/en/guides/cms/ghost

Install the official Ghost Content API client package using Yarn. This package allows your Astro project to interact with your Ghost site's data.

```bash
yarn add @tryghost/content-api
yarn add --dev @types/tryghost__content-api
```

--------------------------------

### Create Astro Project with Blog Template

Source: https://v6.docs.astro.build/en/guides/migrate-to-astro/from-wordpress

Initiates a new Astro project using the official blog starter template. This command can be executed using npm, pnpm, or Yarn. The template provides a pre-configured structure for a blog.

```bash
npm create astro@latest -- --template blog

```

```bash
pnpm create astro@latest --template blog

```

```bash
yarn create astro --template blog

```

--------------------------------

### Scaffold Astro Site with Juno Template

Source: https://v6.docs.astro.build/en/guides/deploy/juno

These commands demonstrate how to quickly scaffold a new Astro website using a pre-made Astro starter template provided by Juno. This is a convenient way to begin a new project with Juno integration.

```bash
npm create juno@latest -- --template astro-starter
```

```bash
pnpm create juno -- --template astro-starter
```

```bash
yarn create juno -- --template astro-starter
```

--------------------------------

### Install Flotiq TypeScript SDK for Astro

Source: https://v6.docs.astro.build/en/guides/cms/flotiq

Install the Flotiq TypeScript SDK to facilitate communication between your Astro project and the Flotiq CMS. This SDK simplifies API interactions.

```bash
npm install flotiq-api-ts
```

```bash
pnpm add flotiq-api-ts
```

```bash
yarn add flotiq-api-ts
```

--------------------------------

### Render Pages with astro/app Module (JavaScript)

Source: https://v6.docs.astro.build/en/reference/adapter-reference

This example shows how to use the `App` constructor from `astro/app` to render requests, including setting up a fetch event listener for incoming requests.

```javascript
import { App } from 'astro/app';
import http from 'http';


export function start(manifest) {
  const app = new App(manifest);


  addEventListener('fetch', event => {
    event.respondWith(
      app.render(event.request)
    );
  });
}
```

--------------------------------

### Install Netlify CLI

Source: https://v6.docs.astro.build/en/guides/deploy/netlify

Installs the Netlify Command Line Interface globally on your system. This tool is used for managing Netlify sites and deployments from the terminal.

```bash
npm install --global netlify-cli
```

--------------------------------

### Install Contentful Dependencies for Astro

Source: https://v6.docs.astro.build/en/guides/cms/contentful

Install the official Contentful JavaScript SDK and the rich-text-html-renderer package for Astro. These are essential for connecting to Contentful and rendering rich text content.

```npm
npm install contentful @contentful/rich-text-html-renderer
```

```pnpm
pnpm add contentful @contentful/rich-text-html-renderer
```

```yarn
yarn add contentful @contentful/rich-text-html-renderer
```

--------------------------------

### Install and Deploy with Vercel CLI

Source: https://v6.docs.astro.build/en/guides/deploy/vercel

Installs the Vercel CLI globally and initiates a deployment. The CLI automatically detects Astro and configures settings.

```bash
npm install -g vercel
vercel
```

```bash
pnpm add -g vercel
vercel
```

```bash
yarn global add vercel
vercel
```

--------------------------------

### Configuring SSR Adapter: Netlify Example

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v3

Demonstrates updating the Astro configuration for the Netlify adapter, replacing the deprecated `build.split` option with the new `functionPerRoute` configuration.

```typescript
import { defineConfig } from "astro/config";
import netlify from "@astrojs/netlify/functions";


export default defineConfig({
     build: {
        split: true
     },
     adapter: netlify({
        functionPerRoute: true
     }),
});
```

--------------------------------

### NodeApp Constructor

Source: https://v6.docs.astro.build/en/reference/adapter-reference

Initializes a NodeApp instance for rendering prebuilt pages in Node.js environments.

```APIDOC
## NodeApp Constructor

### Description
This module is used for rendering pages that have been prebuilt through `astro build`. It allows you to create a `NodeApp` providing all the methods available from `App` and additional methods useful for Node environments.

### Constructor
`new NodeApp(manifest: object, options?: { streaming?: boolean })`

### Parameters
- **manifest** (object) - Required - The SSR manifest argument.
- **options** (object) - Optional - An argument to enable or disable streaming, defaulting to `true`.
  - **streaming** (boolean) - Optional - Whether to enable streaming, defaults to `true`.

### Example
```javascript
import { NodeApp } from 'astro/app/node';

// Assuming 'manifest' is your SSR manifest object
const nodeApp = new NodeApp(manifest);
```
```

--------------------------------

### Install Storyblok Astro Integration with pnpm

Source: https://v6.docs.astro.build/en/guides/cms/storyblok

Installs the official Storyblok integration for Astro and the Vite build tool using pnpm. This command is an alternative to npm for package management.

```bash
pnpm add @storyblok/astro vite
```

--------------------------------

### Get Astro Adapter Logger in JavaScript

Source: https://v6.docs.astro.build/en/reference/adapter-reference

This example shows how to obtain an instance of the Astro logger within an adapter's runtime environment. It includes a try-catch block to demonstrate logging an error message if an operation fails.

```javascript
const logger = app.getAdapterLogger();
try {
  /* Some logic that can throw */
} catch {
  logger.error("Your custom error message using Astro logger.");
}
```

--------------------------------

### Query Turso Database in Astro Component

Source: https://v6.docs.astro.build/en/guides/backend/turso

Import the initialized Turso client and execute a SQL query within an Astro component to fetch data. This example retrieves all posts and displays their titles.

```astro
---
import { turso } from '../turso'


const { rows } = await turso.execute('SELECT * FROM posts')
---


<ul>
  {rows.map((post) => (
    <li>{post.title}</li>
  ))}
</ul>
```

--------------------------------

### Install Storyblok Astro Integration with npm

Source: https://v6.docs.astro.build/en/guides/cms/storyblok

Installs the official Storyblok integration for Astro and the Vite build tool using npm. This is a prerequisite for connecting Astro with your Storyblok space.

```bash
npm install @storyblok/astro vite
```

--------------------------------

### Install Storyblok Astro Integration with Yarn

Source: https://v6.docs.astro.build/en/guides/cms/storyblok

Installs the official Storyblok integration for Astro and the Vite build tool using Yarn. This command is another alternative for package management.

```bash
yarn add @storyblok/astro vite
```

--------------------------------

### Install Nano Stores (Vanilla JS)

Source: https://v6.docs.astro.build/en/recipes/sharing-state-islands

Installs the core Nano Stores library without framework-specific helpers. This is suitable for projects using vanilla JavaScript or when integrating with frameworks not explicitly supported by helper packages.

```bash
npm install nanostores
```

--------------------------------

### Initialize package.json for Astro Project

Source: https://v6.docs.astro.build/en/install-and-setup

Initializes a package.json file to manage project dependencies, including Astro. Supports npm, pnpm, and Yarn.

```bash
npm init --yes
```

```bash
pnpm init
```

```bash
yarn init --yes
```

--------------------------------

### Manually Install Vercel Adapter

Source: https://v6.docs.astro.build/en/guides/integrations-guide/vercel

Installs the `@astrojs/vercel` adapter as a project dependency using a package manager. This is the first step for manual integration.

```bash
npm install @astrojs/vercel
```

```bash
pnpm add @astrojs/vercel
```

```bash
yarn add @astrojs/vercel
```

--------------------------------

### Install @astrojs/svelte using Astro CLI (npm, pnpm, yarn)

Source: https://v6.docs.astro.build/en/guides/integrations-guide/svelte

Automates the setup of the @astrojs/svelte integration by running the 'astro add svelte' command. This is the recommended method for adding official Astro integrations.

```bash
npx astro add svelte

```

```bash
pnpm astro add svelte

```

```bash
yarn astro add svelte

```

--------------------------------

### Configure Astro for Static Hosting on Kinsta

Source: https://v6.docs.astro.build/en/guides/deploy/kinsta

This configuration sets up an Astro project for static hosting on Kinsta Application Hosting. It requires a `name` field in `package.json`, a `build` script, and the `serve` package installed with the `start` script set to `serve dist/`. The `dependencies` should include `astro` and `serve`.

```json
{
  "name": "anything",
  "scripts": {
    "dev": "astro dev",
    "start": "serve dist/",
    "build": "astro build",
    "preview": "astro preview",
    "astro": "astro"
  },
  "dependencies": {
    "astro": "^2.2.0",
    "serve": "^14.0.1"
  }
}
```

--------------------------------

### Query Turso with SQL Placeholders in Astro

Source: https://v6.docs.astro.build/en/guides/backend/turso

Use the execute method with an object containing 'sql' and 'args' to pass variables safely into your SQL statements. This example fetches a single post based on its slug.

```astro
---
import { turso } from '../turso'


const { slug } = Astro.params


const { rows } = await turso.execute({
  sql: 'SELECT * FROM posts WHERE slug = ?',
  args: [slug!]
})
---


<h1>{rows[0].title}</h1>
```

--------------------------------

### Dockerfile for Astro SSR with Node.js

Source: https://v6.docs.astro.build/en/recipes/docker

This Dockerfile builds an Astro site for SSR and serves it using Node.js on port 4321. It requires the Node adapter to be installed in the Astro project. Dependencies are installed, the site is built, and the Node.js server is started.

```Dockerfile
FROM node:lts AS runtime
WORKDIR /app


COPY . .


RUN npm install
RUN npm run build


ENV HOST=0.0.0.0
ENV PORT=4321
EXPOSE 4321
CMD ["node", "./dist/server/entry.mjs"]
```

--------------------------------

### Azion CLI Local Development Output

Source: https://v6.docs.astro.build/en/guides/deploy/azion

Example output from the `azion dev` command, showing the build process and the local server running. It indicates the success of the build step and provides the URL for accessing the application locally.

```text
Building your Edge Application. This process may take a few minutes
Running build step command:
...
[Azion Bundler] [Server] › ✔  success   Function running on port http://localhost:3000
```

--------------------------------

### Fetch and Render Remote Markdown with Marked.js

Source: https://v6.docs.astro.build/en/guides/markdown-content

This example demonstrates fetching Markdown content from a remote URL and rendering it to HTML at runtime using the 'marked' library. It requires the 'marked' package to be installed. The output is an HTML string that can be directly inserted into an Astro component.

```javascript
// Example: Fetch Markdown from a remote API
// and render it to HTML, at runtime.
// Using "marked" (https://github.com/markedjs/marked)
import { marked } from 'marked';
const response = await fetch('https://raw.githubusercontent.com/wiki/adam-p/markdown-here/Markdown-Cheatsheet.md');
const markdown = await response.text();
const content = marked.parse(markdown);

```

```html
<article set:html={content} />
```

--------------------------------

### Install Deno Astro Adapter (pnpm)

Source: https://v6.docs.astro.build/en/guides/deploy/deno

Installs the `@deno/astro-adapter` package using pnpm. This is a prerequisite for enabling on-demand rendering with Deno in an Astro project.

```bash
pnpm install @deno/astro-adapter
```

--------------------------------

### Install Nano Stores for Solid

Source: https://v6.docs.astro.build/en/recipes/sharing-state-islands

Installs the Nano Stores library along with its helper package for Solid. This facilitates state management and sharing across Solid islands in an Astro project.

```bash
npm install nanostores @nanostores/solid
```

--------------------------------

### Run On-Demand Rendered Astro Site with Deno

Source: https://v6.docs.astro.build/en/guides/deploy/deno

Starts the on-demand rendered Astro site using Deno by executing the server entry point. This command is used after building an Astro site configured for server-side rendering with the Deno adapter.

```bash
deno run -A ./dist/server/entry.mjs
```

--------------------------------

### Create Astro Project with Starlight Template using npm

Source: https://v6.docs.astro.build/en/guides/migrate-to-astro/from-pelican

This command initializes a new Astro project using the official Starlight documentation theme starter template via npm. It's a quick way to begin a new project with a pre-configured structure for documentation sites.

```bash
npm create astro@latest -- --template starlight
```

--------------------------------

### Configure Route Prerendering with astro:route:setup Hook

Source: https://v6.docs.astro.build/en/reference/integrations-reference

The 'astro:route:setup' hook in Astro integrations allows modification of route options before they are finalized. This example demonstrates how to conditionally set the 'prerender' property for specific routes, enabling on-demand server rendering for blog posts based on their component path.

```typescript
import { defineConfig } from 'astro/config';


export default defineConfig({
  integrations: [setPrerender()],
});


function setPrerender() {
  return {
    name: 'set-prerender',
    hooks: {
      'astro:route:setup': ({ route }) => {
        if (route.component.endsWith('/blog/[slug].astro')) {
          route.prerender = true;
        }
      },
    },
  };
}
```

--------------------------------

### Install ApostropheCMS Astro Integration Dependencies

Source: https://v6.docs.astro.build/en/guides/cms/apostrophecms

Installs the necessary packages for integrating ApostropheCMS with Astro. This includes the official Apostrophe integration, Vite, and the Astro Node adapter. Choose the command corresponding to your package manager.

```bash
npm install @apostrophecms/apostrophe-astro vite @astrojs/node
```

```bash
pnpm add @apostrophecms/apostrophe-astro vite @astrojs/node
```

```bash
yarn add @apostrophecms/apostrophe-astro vite @astrojs/node
```

--------------------------------

### Install Decap CMS via npm

Source: https://v6.docs.astro.build/en/guides/cms/decap-cms

Installs the Decap CMS application package using npm. This is a common method for adding Decap CMS to an Astro project.

```bash
npm install decap-cms-app
```

--------------------------------

### Install Sentry SDK for Astro

Source: https://v6.docs.astro.build/en/guides/backend/sentry

Installs the Sentry SDK package and adds the Sentry integration to your Astro project. This command is executed via the Astro CLI.

```bash
npx astro add @sentry/astro
```

```bash
pnpm astro add @sentry/astro
```

```bash
yarn astro add @sentry/astro
```

--------------------------------

### Scoped CSS Specificity Example

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

Illustrates the change in scoped CSS specificity in Astro, showing how `:where()` is used to maintain authored specificity instead of increasing it.

```html
<style>
  div { color: red; } /* 0-0-1 specificity */
</style>
```

```css
div~~.astro-XXXXXX~~ { color: red; } /* 0-1-1 specificity */
```

```css
div:where(.astro-XXXXXX) { color: red; } /* 0-0-1 specificity */
```

--------------------------------

### Install Stylus for Astro

Source: https://v6.docs.astro.build/en/guides/styling

Installs the Stylus preprocessor as a project dependency using npm. This enables the use of Stylus syntax within your Astro components.

```bash
npm install stylus

```

--------------------------------

### Install React and ReactDOM peer dependencies

Source: https://v6.docs.astro.build/en/guides/integrations-guide/react

Installs React, ReactDOM, and their type definitions. Required if you encounter 'Cannot find package react' warnings.

```bash
npm install react react-dom @types/react @types/react-dom
```

```bash
pnpm add react react-dom @types/react @types/react-dom
```

```bash
yarn add react react-dom @types/react @types/react-dom
```

--------------------------------

### Install Dependencies

Source: https://v6.docs.astro.build/en/guides/cms/drupal

Instructions for installing npm packages to simplify working with JSON:API requests and responses in Astro.

```APIDOC
## Install Dependencies

### Description
Installs `jsona` and `drupal-jsonapi-params` npm packages to help manage complex JSON:API requests and responses.

### Packages
*   `JSONA`: Serializes and deserializes JSON API v1.0 compliant data.
*   `Drupal JSON-API Params`: A helper class for constructing optimized JSON:API query parameters.

### Installation Commands

**npm:**
```bash
npm install jsona drupal-jsonapi-params
```

**pnpm:**
```bash
pnpm add jsona drupal-jsonapi-params
```

**Yarn:**
```bash
yarn add jsona drupal-jsonapi-params
```
```

--------------------------------

### Heroku Git Remote Setup and App Creation

Source: https://v6.docs.astro.build/en/guides/deploy/heroku

Initializes a Git repository, stages all project files, commits them, creates a new Heroku application with a specified name, and sets the buildpack for static sites.

```shell
# version change
$ git init
$ git add .
$ git commit -m "My site ready for deployment."


# creates a new app with a specified name
$ heroku apps:create example


# set buildpack for static sites
$ heroku buildpacks:set https://github.com/heroku/heroku-buildpack-static.git
```

--------------------------------

### Setting Dynamic Prerender Values with Astro Integrations

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v5

This example demonstrates how to dynamically set 'prerender' values for routes in Astro v5.0 using the `astro:route:setup` hook within a custom integration. This replaces the previous support for dynamic `prerender` exports directly in route files.

```javascript
import { defineConfig } from 'astro/config';
import { loadEnv } from 'vite';


export default defineConfig({
  integrations: [
    {
      name: 'set-prerender',
      hooks: {
        'astro:route:setup': ({ route }) => {
          // Load environment variables from .env files (if needed)
          const { PRERENDER } = loadEnv(process.env.NODE_ENV, process.cwd(), '');
          // Find routes matching the expected filename.
          if (route.component.endsWith('/blog/[slug].astro')) {
            // Set the prerender value on routes as needed.
            route.prerender = PRERENDER;
          }
        },
      },
    }
  ],
});
```

--------------------------------

### Update HTTP Request Methods Case in Astro

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v3

Demonstrates the change in Astro v3.0 where HTTP request methods are now uppercase. The example shows how to rename a lowercase `get` function to its uppercase equivalent `GET`.

```javascript
export function GET() {
    return new Response(JSON.stringify({ "title": "Bob's blog" }));
}
```

--------------------------------

### Install Deno Astro Adapter (Yarn)

Source: https://v6.docs.astro.build/en/guides/deploy/deno

Installs the `@deno/astro-adapter` package using Yarn. This is a prerequisite for enabling on-demand rendering with Deno in an Astro project.

```bash
yarn add @deno/astro-adapter
```

--------------------------------

### Update Astro Configuration for Integrations (astro.config.mjs)

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

Example of updating the `astro.config.mjs` file to use the new integration system, replacing the deprecated `renderers` configuration.

```javascript
// Then, update your `astro.config.mjs` file:
// (Read the full walkthrough: https://docs.astro.build/en/guides/integrations-guide)
import lit from '@astrojs/lit';
import react from '@astrojs/react';


export default {
  renderers: ['@astrojs/renderer-lit', '@astrojs/renderer-react'],
  integrations: [lit(), react()],
}
```

--------------------------------

### Create Astro Project from GitHub Repository (npm)

Source: https://v6.docs.astro.build/en/install-and-setup

This command creates a new Astro project from a GitHub repository. Replace `<github-username>/<github-repo>` with the actual repository details. It uses npm.

```bash
npm create astro@latest -- --template <github-username>/<github-repo>
```

--------------------------------

### Initialize Fleek Site Project

Source: https://v6.docs.astro.build/en/guides/deploy/fleek

Initializes a new Fleek site project, which generates a configuration file. This step is necessary before deploying a site using the Fleek CLI.

```bash
fleek sites init
```

--------------------------------

### Manually install @astrojs/sitemap package

Source: https://v6.docs.astro.build/en/guides/integrations-guide/sitemap

Steps to manually install the @astrojs/sitemap package using npm, pnpm, or yarn.

```bash
npm install @astrojs/sitemap

```

```bash
pnpm add @astrojs/sitemap

```

```bash
yarn add @astrojs/sitemap

```

--------------------------------

### Install Astro Vue Integration using npm, pnpm, or Yarn

Source: https://v6.docs.astro.build/en/guides/integrations-guide/vue

Automates the setup of the @astrojs/vue integration by running the `astro add vue` command. This is the recommended method for adding integrations to your Astro project.

```bash
npx astro add vue
```

```bash
pnpm astro add vue
```

```bash
yarn astro add vue
```

--------------------------------

### Initialize Turso Client in Astro

Source: https://v6.docs.astro.build/en/guides/backend/turso

Create a 'turso.ts' file in the 'src' folder and use createClient from '@libsql/client/web' to initialize the Turso client with your database URL and auth token from environment variables.

```typescript
import { createClient } from "@libsql/client/web";


export const turso = createClient({
  url: import.meta.env.TURSO_DATABASE_URL,
  authToken: import.meta.env.TURSO_AUTH_TOKEN,
});
```

--------------------------------

### Install Decap CMS via Yarn

Source: https://v6.docs.astro.build/en/guides/cms/decap-cms

Installs the Decap CMS application package using Yarn. This provides another option for package management when integrating Decap CMS with Astro.

```bash
yarn add decap-cms-app
```

--------------------------------

### Install Surge CLI Globally

Source: https://v6.docs.astro.build/en/guides/deploy/surge

Installs the Surge Command Line Interface globally on your system using npm. This command is a prerequisite for deploying sites to Surge.

```bash
npm install -g surge
```

--------------------------------

### Install Prettier and Astro Plugin (pnpm)

Source: https://v6.docs.astro.build/en/editor-setup

Installs Prettier and the official Astro Prettier plugin using pnpm. This command ensures that Astro files can be formatted correctly by Prettier.

```bash
pnpm add --save-dev --save-exact prettier prettier-plugin-astro
```

--------------------------------

### Add sitemap URL to robots.txt

Source: https://v6.docs.astro.build/en/guides/integrations-guide/sitemap

Example of how to add the sitemap index URL to your `robots.txt` file to guide search engine crawlers.

```text
User-agent: *
Allow: /


Sitemap: https://<YOUR SITE>/sitemap-index.xml

```

--------------------------------

### Wrangler Configuration for Astro

Source: https://v6.docs.astro.build/en/guides/deploy/cloudflare

Provides example configurations for wrangler.jsonc files, differentiating between static hosting and on-demand rendering setups for Astro projects. Ensure compatibility dates are updated.

```json
{
  "name": "my-astro-app",
  "compatibility_date": "YYYY-MM-DD", // Update to the day you deploy
  "pages_build_output_dir": "./dist"
}
```

```json
{
  "name": "my-astro-app",
  "compatibility_date": "YYYY-MM-DD", // Update to the day you deploy
  "compatibility_flags": [
    "nodejs_compat",
    "disable_nodejs_process_v2"
  ],
  "pages_build_output_dir": "./dist"
}
```

--------------------------------

### Configure Redis Session Driver Options

Source: https://v6.docs.astro.build/en/reference/configuration-reference

Sets driver-specific options for session storage, using Redis as an example. Requires the 'redis' driver to be installed and configured. The URL for the Redis instance is typically provided via environment variables.

```javascript
{
   session: {
     driver: "redis",
     options: {
       url: process.env.REDIS_URL
     },
   }
}
```

--------------------------------

### Configure Astro Project After Integration Removal

Source: https://v6.docs.astro.build/en/guides/integrations-guide

Example of how to update the `astro.config.js` file to remove a previously used integration, like React, from the project's configuration.

```javascript
import { defineConfig } from 'astro/config';


import react from '@astrojs/react';


export default defineConfig({
  integrations: [
    react()
  ]
});
```

--------------------------------

### Configuring SSR Adapter: Vercel Example

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v3

Shows how to update the Astro configuration file to use the new SSR adapter options. This example demonstrates replacing `build.excludeMiddleware` with `edgeMiddleware` for the Vercel adapter.

```typescript
import { defineConfig } from "astro/config";
import vercel from "@astrojs/vercel/serverless";


export default defineConfig({
    build: {
      excludeMiddleware: true
    },
    adapter: vercel({
      edgeMiddleware: true
    }),
});
```

--------------------------------

### Install Better Auth with npm, pnpm, or Yarn

Source: https://v6.docs.astro.build/en/guides/authentication

These commands show how to install the Better Auth package using different package managers. Ensure you have the respective package manager installed on your system before running these commands.

```bash
npm install better-auth
```

```bash
pnpm add better-auth
```

```bash
yarn add better-auth
```

--------------------------------

### Install Cypress for Astro Projects

Source: https://v6.docs.astro.build/en/guides/testing

These commands demonstrate how to install Cypress as a development dependency in an Astro project using different package managers. Installing Cypress locally ensures it's available for running end-to-end tests.

```bash
npm install cypress --save-dev
```

```bash
pnpm add --save-dev cypress
```

```bash
yarn add cypress --dev
```

--------------------------------

### Install @astrojs/alpinejs Integration using npm, pnpm, or Yarn

Source: https://v6.docs.astro.build/en/guides/integrations-guide/alpinejs

Automates the setup of the @astrojs/alpinejs integration for your Astro project. This command adds the necessary dependencies and configuration.

```bash
npx astro add alpinejs
```

```bash
pnpm astro add alpinejs
```

```bash
yarn astro add alpinejs
```

--------------------------------

### Install Playwright using pnpm

Source: https://v6.docs.astro.build/en/guides/testing

Install Playwright within your Astro project using pnpm. This command initializes Playwright and sets up the necessary files for end-to-end testing.

```bash
pnpm create playwright
```

--------------------------------

### Create New Astro Project using npm

Source: https://v6.docs.astro.build/en/guides/migrate-to-astro/from-gatsby

Launches the Astro CLI wizard or creates a new project with a specified template using npm. This command initializes a new Astro project, allowing for either an interactive setup or a pre-defined starter template.

```bash
# launch the Astro CLI Wizard
npm create astro@latest


# create a new project with an official example
npm create astro@latest -- --template <example-name>
```

--------------------------------

### Example generated sitemap-index.xml

Source: https://v6.docs.astro.build/en/guides/integrations-guide/sitemap

An example of the `sitemap-index.xml` file generated by the @astrojs/sitemap integration, which lists all individual sitemap files.

```xml
<?xml version="1.0" encoding="UTF-8"?>
  <sitemapindex xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <sitemap>
    <loc>https://example.com/sitemap-0.xml</loc>
  </sitemap>
</sitemapindex>

```

--------------------------------

### Example of Created Markdown Post

Source: https://v6.docs.astro.build/en/guides/cms/cloudcannon

An example of a Markdown file generated in an Astro project after creating a new entry via CloudCannon. It includes frontmatter with populated data and the Markdown content.

```markdown
---
title: My New Post
author: Sarah
date: 2025-11-12
---


This is my very first post created in CloudCannon. I am **super** excited!
```

--------------------------------

### Configure Vite Plugins with viteConfig()

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

In Astro v0.21+, plugins should now use the `viteConfig()` function for configuration. This example shows how to configure the Svelte renderer using Vite.

```javascript
import { svelte } from '@sveltejs/vite-plugin-svelte';


export default {
  name: '@astrojs/renderer-svelte',
  client: './client.js',
  server: './server.js',
  snowpackPlugin: '@snowpack/plugin-svelte',
  snowpackPluginOptions: { compilerOptions: { hydratable: true } },
  viteConfig() {
    return {
      optimizeDeps: {
        include: ['@astrojs/renderer-svelte/client.js', 'svelte', 'svelte/internal'],
        exclude: ['@astrojs/renderer-svelte/server.js'],
      },
      plugins: [
        svelte({
          emitCss: true,
          compilerOptions: { hydratable: true },
        }),
      ],
    };
  },
}
```

--------------------------------

### Install Prettier and Astro Plugin (npm)

Source: https://v6.docs.astro.build/en/editor-setup

Installs Prettier and the official Astro Prettier plugin using npm. This enables code formatting for Astro files within your project.

```bash
npm install --save-dev --save-exact prettier prettier-plugin-astro
```

--------------------------------

### Display List of Keystatic Posts in Astro

Source: https://v6.docs.astro.build/en/guides/cms/keystatic

Query and display a list of post titles with links to individual post pages using `getCollection` from `astro:content`. This example iterates through posts and creates anchor tags.

```astro
---
import { getCollection } from 'astro:content'


const posts = await getCollection('posts')
---
<ul>
  {posts.map(post => (
    <li>
      <a href={`/posts/${post.slug}`}>{post.data.title}</a>
    </li>
  ))}
</ul>

```

--------------------------------

### Create New Astro Project using pnpm

Source: https://v6.docs.astro.build/en/guides/migrate-to-astro/from-gatsby

Launches the Astro CLI wizard or creates a new project with a specified template using pnpm. This command initializes a new Astro project, allowing for either an interactive setup or a pre-defined starter template.

```bash
# launch the Astro CLI Wizard
pnpm create astro@latest


# create a new project with an official example
pnpm create astro@latest --template <example-name>
```

--------------------------------

### Install Astro Project Dependencies

Source: https://v6.docs.astro.build/en/install-and-setup

Installs Astro as a local project dependency using npm, pnpm, or Yarn. It's crucial to install locally, not globally.

```bash
npm install astro
```

```bash
pnpm add astro
```

```bash
yarn add astro
```

--------------------------------

### Manually install @astrojs/react package

Source: https://v6.docs.astro.build/en/guides/integrations-guide/react

Installs the @astrojs/react package manually. This is an alternative to the automated 'astro add' command.

```bash
npm install @astrojs/react
```

```bash
pnpm add @astrojs/react
```

```bash
yarn add @astrojs/react
```

--------------------------------

### Create New Astro + Keystatic Project

Source: https://v6.docs.astro.build/en/guides/cms/keystatic

Use the Keystatic CLI to generate a new Astro project with Keystatic pre-configured. This command initiates the project creation process.

```bash
npm create @keystatic@latest
```

```bash
pnpm create @keystatic@latest
```

```bash
yarn create @keystatic
```

--------------------------------

### Manually Install @astrojs/node Adapter

Source: https://v6.docs.astro.build/en/guides/integrations-guide/node

Manually install the Node adapter by adding `@astrojs/node` to your project's dependencies using npm, pnpm, or Yarn. Then, configure your `astro.config.*` file to use the adapter.

```bash
npm install @astrojs/node
```

```bash
pnpm add @astrojs/node
```

```bash
yarn add @astrojs/node
```

```javascript
import { defineConfig } from 'astro/config';
import node from '@astrojs/node';


export default defineConfig({
  adapter: node({
    mode: 'standalone',
  }),
});
```

--------------------------------

### Customize Integrations with Factory Function Options

Source: https://v6.docs.astro.build/en/guides/integrations-guide

Integrations often act as factory functions, allowing you to pass arguments and options to customize their behavior. This example shows how to configure the `sitemap` integration with a `filter` option.

```javascript
integrations: [
  // Example: Customize your integration with function arguments
  sitemap({filter: true})
]

```

--------------------------------

### Configure Image Endpoint Route and Entrypoint in Astro

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v5

Astro 5.0 allows for more granular control over the image optimization endpoint. You can now specify both a `route` and an `entrypoint` in the `image.endpoint` configuration. This is useful if the default `/_image` route conflicts with your project setup. The example demonstrates how to migrate from the previous `image.endpoint` configuration to the new structure.

```typescript
import { defineConfig } from "astro/config";


defineConfig({
  image: {
    endpoint: './src/image-endpoint.ts',
    endpoint: {
      route: "/image",
      entrypoint: "./src/image_endpoint.ts"
    }
  },
})
```

--------------------------------

### Install Astro Project Dependencies with Yarn

Source: https://v6.docs.astro.build/en/install-and-setup

Use this command to install all required dependencies for your Astro project with Yarn. This is necessary if you skipped the dependency installation step in the CLI wizard.

```bash
yarn install
```

--------------------------------

### Create Astro Project from GitHub Repository (pnpm)

Source: https://v6.docs.astro.build/en/install-and-setup

This command creates a new Astro project from a specified GitHub repository using pnpm. The `--template` flag accepts the GitHub username and repository name.

```bash
pnpm create astro@latest --template <github-username>/<github-repo>
```

--------------------------------

### Execute Code After Page Load/Navigation (JavaScript)

Source: https://v6.docs.astro.build/en/guides/view-transitions

This example demonstrates how to use the `astro:page-load` event to execute code after a new page is visible and its styles/scripts are loaded. It's ideal for re-initializing event listeners or other setup tasks on every navigation.

```javascript
<script>
  document.addEventListener("astro:page-load", () => {
    // This runs on first page load and after every navigation.
    setupStuff(); // e.g. add event listeners
  });
</script>
```

--------------------------------

### Enable Autoprefixer in PostCSS Configuration

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

Autoprefixer is no longer enabled by default in Astro v0.21+. To enable it, install the `autoprefixer` package and create a `postcss.config.cjs` file.

```javascript
module.exports = {
  plugins: {
    autoprefixer: {},
  },
};
```

--------------------------------

### Manually Install @astrojs/mdx Package

Source: https://v6.docs.astro.build/en/guides/integrations-guide/mdx

Install the @astrojs/mdx package using npm, pnpm, or Yarn. After installation, apply the integration in your `astro.config.*` file by adding `mdx()` to the `integrations` array.

```bash
npm install @astrojs/mdx
```

```bash
pnpm add @astrojs/mdx
```

```bash
yarn add @astrojs/mdx
```

--------------------------------

### Migrating from Astro.fetchContent to Astro.glob

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

Provides a direct comparison between the old `Astro.fetchContent()` method (v0.25) and the new `Astro.glob()` API (v0.26+) for importing markdown files. It highlights the change in how frontmatter is accessed.

```javascript
// v0.25
let allPosts = Astro.fetchContent('./posts/*.md');
// v0.26+
let allPosts = await Astro.glob('./posts/*.md');
```

```javascript
// When migrating, be careful about the new Markdown object interface. Frontmatter, for example, has been moved to the `.frontmatter` property, so references like `post.title` should change to `post.frontmatter.title`.
```

--------------------------------

### Install Nano Stores for Preact

Source: https://v6.docs.astro.build/en/recipes/sharing-state-islands

Installs the Nano Stores library along with its helper package for Preact. This enables the use of Nano Stores for state management within Preact components in an Astro project.

```bash
npm install nanostores @nanostores/preact
```

--------------------------------

### Juno CLI Deployment Commands

Source: https://v6.docs.astro.build/en/guides/deploy/juno

This section provides the commands to log in to the Juno CLI and deploy your site. Running `juno login` will open a browser window for authorization. `juno hosting deploy` initiates the deployment process.

```bash
juno login
```

```bash
juno hosting deploy
```

--------------------------------

### Display Blog Posts List in Astro

Source: https://v6.docs.astro.build/en/guides/cms/flotiq

Render a list of blog posts on an Astro page, displaying the title, creation date, and content of each post. This example iterates through fetched posts and creates links to individual post pages.

```astro
---
import { flotiq } from "../lib/flotiq";


const posts = await flotiq.BlogpostAPI.list();
---
<html lang="en">
  <head>
    <title>Astro</title>
  </head>
  <body>
    {posts.data?.map((post) => (
      <section>
        <a href={`/posts/${post.slug}`}>
          <h2>{post.title}</h2>
        </a>
        <div>{post.internal?.createdAt}</div>
        <div set:html={post.content}/>
      </section>
    ))}
  </body>
</html>

```

--------------------------------

### Install Sharp Image Service Dependency (pnpm)

Source: https://v6.docs.astro.build/en/guides/images

This command installs the Sharp package using pnpm. Sharp is the default image service for `astro:assets`. Manual installation might be necessary with strict package managers like pnpm, even though Sharp is an Astro dependency.

```bash
pnpm add sharp
```

--------------------------------

### GitHub Actions Workflow for Juno Deployment

Source: https://v6.docs.astro.build/en/guides/deploy/juno

This GitHub Actions workflow automates the deployment of your Astro site to Juno. It checks out the repository, sets up Node.js, installs dependencies, and then uses the `junobuild/juno-action` to deploy your site. The `JUNO_TOKEN` secret must be configured in your GitHub repository.

```yaml
name: Deploy to Juno


on:
  workflow_dispatch:
  push:
    branches: [main]


jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Check out the repo
        uses: actions/checkout@v4


      - uses: actions/setup-node@v4
        with:
          node-version: 24
          registry-url: "https://registry.npmjs.org"


      - name: Install Dependencies
        run: npm ci


      - name: Deploy to Juno
        uses: junobuild/juno-action@main
        with:
          args: hosting deploy
        env:
          JUNO_TOKEN: ${{ secrets.JUNO_TOKEN }}
```

--------------------------------

### Initialize Astro Sitecore Project with npx

Source: https://v6.docs.astro.build/en/guides/cms/sitecore

This command initializes a new Astro project integrated with Sitecore JSS. Ensure you have Node.js and npm/npx installed. The command prompts for necessary configuration details to set up your project.

```bash
npx @astro-sitecore-jss/create-astro-sitecore-jss@latest
```

--------------------------------

### Configure Local Font Provider (TypeScript)

Source: https://v6.docs.astro.build/en/reference/experimental-flags/fonts

Example of configuring local font files in Astro's configuration. This setup uses the 'local' provider and specifies the font name and its corresponding CSS variable.

```typescript
import { defineConfig } from "astro/config"


export default defineConfig({
  experimental: {
    fonts: [{
      provider: "local",
      name: "Roboto",
      cssVariable: "--font-roboto"
    }]
  }
});
```

--------------------------------

### Drupal Authentication Setup

Source: https://v6.docs.astro.build/en/guides/cms/drupal

Information on setting up authentication for Drupal's JSON:API if needed, and how to add credentials to your Astro project's .env file.

```APIDOC
## Set Up Drupal Credentials

### Description
By default, Drupal's JSON:API is accessible without authentication. This section details how to configure authentication methods if you need to restrict access or modify data.

### Default Access
External data-fetching requests can access Drupal content without credentials. This does not allow modification of data or site settings.

### Authentication Methods
Drupal supports several authentication methods:
  * Basic Authentication
  * API Key-based authentication
  * Access Token/OAuth-based authentication
  * JWT Token-based authentication
  * Third-Party Provider token authentication

### Adding Credentials to .env
To use authentication, add your credentials to the `.env` file in your Astro project's root directory. Examples:

```
DRUPAL_BASIC_USERNAME="editor"
DRUPAL_BASIC_PASSWORD="editor"
DRUPAL_JWT_TOKEN="abc123"
```

Refer to Astro's documentation for more details on using environment variables.
```

--------------------------------

### Create Astro Project with React and Partytown (npm)

Source: https://v6.docs.astro.build/en/install-and-setup

This command creates a new Astro project and simultaneously installs the React and Partytown integrations using npm. The `--add` flag specifies the integrations to include.

```bash
npm create astro@latest -- --add react --add partytown
```

--------------------------------

### Configure Google Font Provider (TypeScript)

Source: https://v6.docs.astro.build/en/reference/experimental-flags/fonts

Example of configuring the Google font provider in Astro's configuration file. This setup specifies the font provider, font name, and the CSS variable to be used for the font.

```typescript
import { defineConfig, fontProviders } from "astro/config"


export default defineConfig({
  experimental: {
    fonts: [{
      provider: fontProviders.google(),
      name: "Roboto",
      cssVariable: "--font-roboto"
    }]
  }
});
```

--------------------------------

### Create Astro Project with React and Partytown (pnpm)

Source: https://v6.docs.astro.build/en/install-and-setup

This command creates a new Astro project and installs React and Partytown integrations using pnpm. The `--add` flag is used to specify the integrations.

```bash
pnpm create astro@latest --add react --add partytown
```

--------------------------------

### Add Partytown Integration to Astro Project

Source: https://v6.docs.astro.build/en/guides/integrations-guide/partytown

Automates the setup of the Partytown integration for your Astro project. This command adds the necessary dependencies and configuration. It's the recommended way to install the integration.

```bash
npx astro add partytown
```

```bash
pnpm astro add partytown
```

```bash
yarn astro add partytown
```

--------------------------------

### Astro Integration Setup (JavaScript)

Source: https://v6.docs.astro.build/en/reference/dev-toolbar-app-reference

Sets up an Astro integration, providing a basic structure for hooks. It includes placeholders for `astro:config:setup` and `astro:server:setup`, where toolbar interactions can be managed.

```javascript
export default () => ({
  name: "my-integration",
  hooks: {
    "astro:config:setup": ({ addDevToolbarApp }) => {},
    "astro:server:setup": ({ toolbar }) => {},
  },
});
```

--------------------------------

### Install Fleek CLI

Source: https://v6.docs.astro.build/en/guides/deploy/fleek

Installs the Fleek CLI tool globally using npm. This command requires Node.js version 18.18.2 or higher.

```bash
npm install -g @fleek-platform/cli
```

--------------------------------

### Display Single Astro Content Entry with <Content /> Component

Source: https://v6.docs.astro.build/en/guides/cms/keystatic

This snippet demonstrates how to fetch and render a single content entry from Astro's content collections. It imports `getEntry` to retrieve a specific post and then uses the `render()` method to get the `Content` component for displaying the post's body. This is useful for individual blog posts or pages.

```astro
import { getEntry } from 'astro:content'


const post = await getEntry('posts', 'my-first-post')
const { Content } = await post.render()


<main>
  <h1>{post.data.title}</h1>
  <Content />
</main>
```

--------------------------------

### Install Zeabur Astro Adapter (npm)

Source: https://v6.docs.astro.build/en/guides/deploy/zeabur

Installs the official Zeabur adapter for Astro projects. This is a prerequisite for enabling Server-Side Rendering (SSR) capabilities when deploying to Zeabur. It is installed using npm.

```bash
npm install @zeabur/astro-adapter
```

--------------------------------

### Manually Install Cloudflare Adapter with npm

Source: https://v6.docs.astro.build/en/guides/integrations-guide/cloudflare

Manually installs the @astrojs/cloudflare adapter using npm. This involves adding the package as a dependency and then configuring it in your astro.config.mjs file.

```bash
npm install @astrojs/cloudflare
```

--------------------------------

### Configure Astro Scripts in package.json

Source: https://v6.docs.astro.build/en/install-and-setup

Replaces the placeholder 'scripts' section in package.json with essential Astro commands for development, building, and previewing.

```json
{
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "dev": "astro dev",
    "build": "astro build",
    "preview": "astro preview"
  }
}
```

--------------------------------

### Update Astro SSR Start Script (JSON)

Source: https://v6.docs.astro.build/en/guides/deploy/zerops

Updates the 'start' script in package.json to run the Node adapter's server output, essential for Astro SSR deployments.

```json
"scripts": {
  "start": "node ./dist/server/entry.mjs",
}

```

--------------------------------

### Apply remark plugin to MDX integration in Astro

Source: https://v6.docs.astro.build/en/guides/markdown-content

This example demonstrates how to apply a custom remark plugin, `exampleRemarkPlugin`, to MDX files by configuring it within the `mdx` integration options in `astro.config.mjs`.

```javascript
import { defineConfig } from 'astro/config';
import { exampleRemarkPlugin } from './example-remark-plugin.mjs';


export default defineConfig({
  integrations: [
    mdx({
      remarkPlugins: [exampleRemarkPlugin],
    }),
  ],
});
```

--------------------------------

### Install Playwright using npm

Source: https://v6.docs.astro.build/en/guides/testing

Install Playwright within your Astro project using npm. This command initializes Playwright and sets up the necessary files for end-to-end testing.

```bash
npm init playwright@latest
```

--------------------------------

### User Sign-out API

Source: https://v6.docs.astro.build/en/guides/backend/supabase

This endpoint handles user sign-out. It accepts a GET request and removes the user's authentication tokens from the cookies, redirecting them to the sign-in page.

```APIDOC
## GET /api/auth/signout

### Description
Signs out the currently authenticated user by deleting their session tokens.

### Method
GET

### Endpoint
/api/auth/signout

### Parameters
None

### Request Example
```
GET /api/auth/signout
```

### Response
#### Success Response (200)
Redirects to the sign-in page after deleting `sb-access-token` and `sb-refresh-token` cookies.
```

--------------------------------

### Configure Tailwind CSS with PostCSS

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

PostCSS is now a requirement for Tailwind CSS in Astro v0.21+. Ensure PostCSS is installed and configure `postcss.config.cjs` to include Tailwind CSS.

```javascript
module.exports = {
  plugins: {
    tailwindcss: {},
  },
};
```

--------------------------------

### Astro Component Setup and Data Definition

Source: https://v6.docs.astro.build/en/tutorial/6-islands/3

This Astro component sets up the basic layout and defines page-specific data including title, identity, skills, and status flags. It utilizes frontmatter for metadata and JavaScript variables for dynamic content.

```astro
import BaseLayout from "../layouts/BaseLayout.astro";
const pageTitle = "About Me";


const identity = {
  firstName: "Sarah",
  country: "Canada",
  occupation: "Technical Writer",
  hobbies: ["photography", "birdwatching", "baseball"],
};


const skills = ["HTML", "CSS", "JavaScript", "React", "Astro", "Writing Docs"];


const happy = true;
const finished = false;
const finished = true;
const goal = 3;


const skillColor = "crimson";
const fontWeight = "bold";
const textCase = "uppercase";

```

--------------------------------

### Create Astro Project with Starlight Template using pnpm

Source: https://v6.docs.astro.build/en/guides/migrate-to-astro/from-pelican

This command initializes a new Astro project using the official Starlight documentation theme starter template via pnpm. It's an alternative to npm for package management, offering similar functionality for project setup.

```bash
pnpm create astro@latest --template starlight
```

--------------------------------

### Run Astro Preview with Deno (Yarn)

Source: https://v6.docs.astro.build/en/guides/deploy/deno

Executes the `preview` script using Yarn to start the Astro development server with Deno. This command is used after configuring the preview script for Deno.

```bash
yarn run preview
```

--------------------------------

### Install Tina CMS CLI for Astro Projects

Source: https://v6.docs.astro.build/en/guides/cms/tina-cms

Installs the TinaCMS CLI to your Astro project. This command initializes TinaCMS, creating necessary configuration files and sample content.

```bash
npx @tinacms/cli@latest init
```

```bash
pnpm dlx @tinacms/cli@latest init
```

```bash
yarn dlx @tinacms/cli@latest init
```

--------------------------------

### Preview Astro Project Locally with Wrangler

Source: https://v6.docs.astro.build/en/guides/deploy/cloudflare

Builds the Astro project and then starts a local development server using Wrangler Pages. Supports npm, pnpm, and Yarn.

```bash
npx astro build && wrangler pages dev ./dist
```

```bash
pnpm astro build && wrangler pages dev ./dist
```

```bash
yarn astro build && wrangler pages dev ./dist
```

--------------------------------

### Install Astro Integrations and Frameworks with npm

Source: https://v6.docs.astro.build/en/guides/troubleshooting

This command installs the necessary packages for using React with Astro, including the Astro React integration and the React and ReactDOM libraries. Ensure these are installed together for proper functionality.

```bash
npm install @astrojs/react react react-dom
```

--------------------------------

### Configure Flotiq SDK in Astro

Source: https://v6.docs.astro.build/en/guides/cms/flotiq

Initialize the Flotiq API client in your Astro project by creating a configuration file (`flotiq.ts`) and instantiating `FlotiqApi` with your API key. This setup allows for easy access to Flotiq data throughout your application.

```typescript
import { FlotiqApi } from "flotiq-api-ts";


export const flotiq = new FlotiqApi(import.meta.env.FLOTIQ_API_KEY);
```

--------------------------------

### Query Database Client with Node.js (pg)

Source: https://v6.docs.astro.build/en/guides/backend/prisma-postgres

Connect to a PostgreSQL database using the 'pg' client and fetch data. This example demonstrates creating a table, inserting data, and selecting it. It requires the 'pg' package and a DATABASE_URL environment variable.

```javascript
import { Client } from 'pg';
const client = new Client({
  connectionString: import.meta.env.DATABASE_URL,
  ssl: { rejectUnauthorized: false }
});
await client.connect();


await client.query(`
  CREATE TABLE IF NOT EXISTS posts (
    id SERIAL PRIMARY KEY,
    title TEXT UNIQUE,
    content TEXT
  );


  INSERT INTO posts (title, content)
  VALUES ('Hello', 'World')
  ON CONFLICT (title) DO NOTHING;
`);


const { rows } = await client.query('SELECT * FROM posts');
await client.end();
```

--------------------------------

### Astro `astro:config:setup` Hook

Source: https://v6.docs.astro.build/en/reference/integrations-reference

The `astro:config:setup` hook is executed during initialization, before Vite or Astro configurations are resolved. It's used to extend project configuration, such as updating Astro config, applying Vite plugins, adding renderers, and injecting scripts.

```typescript
'astro:config:setup'?: (options: {
  config: AstroConfig;
  command: 'dev' | 'build' | 'preview' | 'sync';
  isRestart: boolean;
  updateConfig: (newConfig: DeepPartial<AstroConfig>) => AstroConfig;
  addRenderer: (renderer: AstroRenderer) => void;
  addClientDirective: (directive: ClientDirectiveConfig) => void;
  addMiddleware: (middleware: AstroIntegrationMiddleware) => void;
  addDevToolbarApp: (entrypoint: DevToolbarAppEntry) => void;
  addWatchFile: (path: URL | string) => void;
  injectScript: (stage: InjectedScriptStage, content: string) => void;
  injectRoute: (injectedRoute: InjectedRoute) => void;
  createCodegenDir: () => URL;
  logger: AstroIntegrationLogger;
}) => void | Promise<void>;
```

--------------------------------

### Install Nano Stores for Astro Projects

Source: https://v6.docs.astro.build/en/recipes/sharing-state

Install the Nano Stores library using your preferred package manager. This is the first step to enabling shared client-side state management in your Astro website.

```bash
npm install nanostores
```

```bash
pnpm add nanostores
```

```bash
yarn add nanostores
```

--------------------------------

### Fetch and Display WordPress Posts in Astro

Source: https://v6.docs.astro.build/en/guides/cms/wordpress

Fetches a list of posts from the WordPress REST API and renders their titles and content using Astro's `set:html` directive. This example assumes a standard WordPress setup.

```astro
---
const res = await fetch("https://[YOUR-SITE]/wp-json/wp/v2/posts");
const posts = await res.json();
---
<h1>Astro + WordPress 🚀</h1>
{
  posts.map((post) => (
      <h2 set:html={post.title.rendered} />
      <p set:html={post.content.rendered} />
  ))
}

```

--------------------------------

### Deploy Site with Netlify CLI

Source: https://v6.docs.astro.build/en/guides/integrations-guide/netlify

Deploys the Astro site to Netlify after the build process, utilizing the generated Netlify Functions and Edge Functions.

```bash
netlify deploy

```

--------------------------------

### Define BlogPost Interface and Contentful Client (TypeScript)

Source: https://v6.docs.astro.build/en/guides/cms/contentful

Defines the `BlogPost` interface to match Contentful content types and initializes the Contentful client. This setup is crucial for type-safe data fetching from Contentful.

```typescript
import * as contentful from "contentful";
import type { EntryFieldTypes } from "contentful";


export interface BlogPost {
  contentTypeId: "blogPost",
  fields: {
    title: EntryFieldTypes.Text
    content: EntryFieldTypes.RichText,
    date: EntryFieldTypes.Date,
    description: EntryFieldTypes.Text,
    slug: EntryFieldTypes.Text
  }
}


export const contentfulClient = contentful.createClient({
  space: import.meta.env.CONTENTFUL_SPACE_ID,
  accessToken: import.meta.env.DEV
    ? import.meta.env.CONTENTFUL_PREVIEW_TOKEN
    : import.meta.env.CONTENTFUL_DELIVERY_TOKEN,
  host: import.meta.env.DEV ? "preview.contentful.com" : "cdn.contentful.com",
});

```

--------------------------------

### Example generated sitemap-0.xml

Source: https://v6.docs.astro.build/en/guides/integrations-guide/sitemap

An example of a `sitemap-0.xml` file generated by the @astrojs/sitemap integration, listing the URLs of the pages on your site.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9" xmlns:news="http://www.google.com/schemas/sitemap-news/0.9" xmlns:xhtml="http://www.w3.org/1999/xhtml" xmlns:image="http://www.google.com/schemas/sitemap-image/1.1" xmlns:video="http://www.google.com/schemas/sitemap-video/1.1">
  <url>
    <loc>https://example.com/</loc>
  </url>
  <url>
    <loc>https://example.com/second-page/</loc>
  </url>
</urlset>

```

--------------------------------

### Create Astro Blog Project with Yarn

Source: https://v6.docs.astro.build/en/guides/migrate-to-astro/from-eleventy

This command initializes a new Astro project using the 'blog' template with Yarn. It's another popular package manager for JavaScript projects.

```bash
yarn create astro --template blog
```

--------------------------------

### Manage Cookies in Astro Pages

Source: https://v6.docs.astro.build/en/guides/on-demand-rendering

Demonstrates how to check, get, set, and delete cookies within an Astro page rendered on demand. This example increments a counter stored in a cookie for each page view.

```javascript
---
export const prerender = false; // Not needed in 'server' mode


let counter = 0


if (Astro.cookies.has('counter')) {
  const cookie = Astro.cookies.get('counter')
  const value = cookie?.number()
  if (value !== undefined && !isNaN(value)) counter = value + 1
}


Astro.cookies.set('counter', String(counter))
---
<html>
  <h1>Counter = {counter}</h1>
</html>

```

--------------------------------

### Build Astro Site with Node.js and npm

Source: https://v6.docs.astro.build/en/guides/deploy/buddy

This snippet demonstrates the commands to install dependencies and build an Astro site using npm within a Node.js environment. It's a common step in CI/CD pipelines for Astro projects.

```shell
npm install
npm run build
```

--------------------------------

### Create Astro Adapter with Server Entrypoint and Static Output

Source: https://v6.docs.astro.build/en/reference/adapter-reference

This code snippet demonstrates how to create a basic Astro adapter. It defines the adapter's name, sets a server entrypoint for on-demand rendering, and declares stable support for Astro's static output feature using the `setAdapter()` function within the `astro:config:done` hook.

```javascript
export default function createIntegration() {
  return {
    name: '@example/my-adapter',
    hooks: {
      'astro:config:done': ({ setAdapter }) => {
        setAdapter({
          name: '@example/my-adapter',
          serverEntrypoint: '@example/my-adapter/server.js',
          supportedAstroFeatures: {
            staticOutput: 'stable'
          }
        });
      },
    },
  };
}
```

--------------------------------

### Create New Astro Project with Bun

Source: https://v6.docs.astro.build/en/recipes/bun

Command to create a new Astro project using Bun. Ensure Bun is installed locally before running this command.

```bash
bun create astro my-astro-project-using-bun
```

--------------------------------

### Install Playwright using Yarn

Source: https://v6.docs.astro.build/en/guides/testing

Install Playwright within your Astro project using Yarn. This command initializes Playwright and sets up the necessary files for end-to-end testing.

```bash
yarn create playwright
```

--------------------------------

### Update Frontmatter for Layout (Astro)

Source: https://v6.docs.astro.build/en/tutorial/6-islands/4

This example shows the removal of the `layout` property from individual Markdown post frontmatter. With content collections and the new rendering approach, the layout is applied programmatically in the page generation file, making this frontmatter definition redundant.

```markdown
---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'My First Blog Post'
pubDate: 2022-07-01
...
---
```

--------------------------------

### Dynamic Routing for JSON Endpoints in Astro

Source: https://v6.docs.astro.build/en/guides/endpoints

This example demonstrates dynamic routing for Astro endpoints. It uses getStaticPaths() to define multiple parameter values and exports a GET function that accesses these parameters via the 'params' object to generate unique JSON responses for each route.

```typescript
import type { APIRoute } from "astro";


const usernames = ["Sarah", "Chris", "Yan", "Elian"];


export const GET: APIRoute = ({ params, request }) => {
  const id = params.id;


  return new Response(
    JSON.stringify({
      name: usernames[id],
    }),
  );
};


export function getStaticPaths() {
  return [
    { params: { id: "0" } },
    { params: { id: "1" } },
    { params: { id: "2" } },
    { params: { id: "3" } },
  ];
}
```

--------------------------------

### Listen to astro:page-load for Script Execution

Source: https://v6.docs.astro.build/en/guides/view-transitions

This example demonstrates how to wrap a script in an event listener for `astro:page-load`. This ensures the script runs after page navigation, making it responsive to user interactions like clicking a hamburger menu, mimicking browser behavior.

```javascript
document.addEventListener("astro:page-load", () => {
  document.querySelector(".hamburger").addEventListener("click", () => {
    document.querySelector(".nav-links").classList.toggle("expanded");
  });
});
```

--------------------------------

### Install Less for Astro

Source: https://v6.docs.astro.build/en/guides/styling

Installs the Less preprocessor as a project dependency using npm. This allows you to write styles using Less syntax in your Astro components.

```bash
npm install less

```

--------------------------------

### Implement custom routing logic with manual i18n middleware

Source: https://v6.docs.astro.build/en/guides/internationalization

Demonstrates how to use Astro's `defineMiddleware` and `redirectToDefaultLocale` for custom routing logic when `routing: "manual"` is enabled. This example redirects requests not starting with '/about' to the default locale.

```javascript
import { defineMiddleware } from "astro:middleware";
import { redirectToDefaultLocale } from "astro:i18n"; // function available with `manual` routing
export const onRequest = defineMiddleware(async (ctx, next) => {
  if (ctx.url.startsWith("/about")) {
    return next();
  } else {
    return redirectToDefaultLocale(302);
  }
})
```

--------------------------------

### Load Environment Variables in Astro Config (Vite)

Source: https://v6.docs.astro.build/en/guides/environment-variables

Demonstrates how to load environment variables within the Astro configuration file (`astro.config.mjs`) using Vite's `loadEnv` helper. This is useful for accessing variables set in `.env` files before the application starts. Requires `vite` to be installed if using `pnpm`.

```javascript
import { loadEnv } from "vite";


const { SECRET_PASSWORD } = loadEnv(process.env.NODE_ENV, process.cwd(), "");
```

--------------------------------

### Integrate Astro Node Handler with Fastify

Source: https://v6.docs.astro.build/en/guides/integrations-guide/node

This example shows how to integrate the Astro Node adapter's handler with a Fastify server. It includes registering Fastify plugins for static file serving and middleware, then applying the `ssrHandler` to handle requests.

```javascript
import Fastify from 'fastify';
import fastifyMiddie from '@fastify/middie';
import fastifyStatic from '@fastify/static';
import { fileURLToPath } from 'node:url';
import { handler as ssrHandler } from './dist/server/entry.mjs';


const app = Fastify({ logger: true });


await app
  .register(fastifyStatic, {
    root: fileURLToPath(new URL('./dist/client', import.meta.url)),
  })
  .register(fastifyMiddie);
app.use(ssrHandler);


app.listen({ port: 8080 });

```

--------------------------------

### Fetch Data in Framework Component (Preact Example)

Source: https://v6.docs.astro.build/en/guides/data-fetching

Shows how to use the global `fetch()` function within a framework component (Preact in this example) to retrieve data. The fetched data is then processed and can be rendered within the component. Fetch calls in framework components behave similarly to Astro components regarding build time vs. runtime execution.

```javascript
import type { FunctionalComponent } from 'preact';


const data = await fetch('https://example.com/movies.json').then((response) => response.json());


// Components that are build-time rendered also log to the CLI.
// When rendered with a `client:*` directive, they also log to the browser console.
console.log(data);


const Movies: FunctionalComponent = () => {
  // Output the result to the page
  return <div>{JSON.stringify(data)}</div>;
};


export default Movies;

```

--------------------------------

### Install Astro TypeScript Plugin with pnpm

Source: https://v6.docs.astro.build/en/guides/typescript

This command installs the Astro TypeScript plugin using pnpm. This is an alternative package manager for installing the necessary plugin to enable advanced TypeScript features in your Astro project.

```bash
pnpm add @astrojs/ts-plugin
```

--------------------------------

### Manually Install Cloudflare Adapter with pnpm

Source: https://v6.docs.astro.build/en/guides/integrations-guide/cloudflare

Manually installs the @astrojs/cloudflare adapter using pnpm. This involves adding the package as a dependency and then configuring it in your astro.config.mjs file.

```bash
pnpm add @astrojs/cloudflare
```

--------------------------------

### astro:server:start Hook

Source: https://v6.docs.astro.build/en/reference/integrations-reference

The `astro:server:start` hook is called just after the dev server's `listen()` event fires, allowing interception of network requests.

```APIDOC
## astro:server:start

### Description
Called just after the server’s `listen()` event has fired. Use this to intercept network requests at the specified address. Consider `astro:server:setup` for middleware.

### Method
`'astro:server:start'?: (options: { address: AddressInfo; logger: AstroIntegrationLogger; }) => void | Promise<void>;`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
// Example usage within an integration
{
  name: 'my-integration',
  hooks: {
    'astro:server:start': async ({ address, logger }) => {
      logger.info(`Server listening on ${address.port}`);
    }
  }
}
```

### Response
#### Success Response (200)
None

#### Response Example
None
```

--------------------------------

### Astro Markdown Frontmatter Example

Source: https://v6.docs.astro.build/en/guides/cms/cloudcannon

An example of frontmatter for a Markdown file within an Astro content collection, used as a CloudCannon schema template. It includes placeholders for title, author, and date.

```markdown
---
title:
author:
date:
---
```

--------------------------------

### Update astro:build:setup hook for Vite Environments (Astro Integration API)

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v6

In Astro 6.0, the `astro:build:setup` hook is called once with all environments. The `target` parameter is removed, and `vite.environments` should be used to configure specific environments. This change is necessary for compatibility with Vite's new Environment API.

```javascript
hooks: {
  'astro:build:setup': ({ target, vite }) => {
    if (target === 'client') {
      vite.build.minify = false;
    }
  }
}
```

```javascript
hooks: {
  'astro:build:setup': ({ vite }) => {
    vite.environments.client.build.minify = false;
  }
}
```

--------------------------------

### Manually Install Cloudflare Adapter with Yarn

Source: https://v6.docs.astro.build/en/guides/integrations-guide/cloudflare

Manually installs the @astrojs/cloudflare adapter using Yarn. This involves adding the package as a dependency and then configuring it in your astro.config.mjs file.

```bash
yarn add @astrojs/cloudflare
```

--------------------------------

### Manually Install @astrojs/solid-js Package

Source: https://v6.docs.astro.build/en/guides/integrations-guide/solid-js

Installs the @astrojs/solid-js package manually using npm, pnpm, or Yarn. This is an alternative to the automated `astro add` command.

```bash
npm install @astrojs/solid-js
```

```bash
pnpm add @astrojs/solid-js
```

```bash
yarn add @astrojs/solid-js
```

--------------------------------

### Run Astro Preview with Deno (pnpm)

Source: https://v6.docs.astro.build/en/guides/deploy/deno

Executes the `preview` script using pnpm to start the Astro development server with Deno. This command is used after configuring the preview script for Deno.

```bash
pnpm run preview
```

--------------------------------

### Configure Netlify Adapter for Deployment

Source: https://v6.docs.astro.build/en/reference/configuration-reference

Example configuration for deploying an Astro project to Netlify using the official adapter. This enables serverless deployment and on-demand rendering capabilities.

```javascript
import netlify from '@astrojs/netlify';
{
  // Example: Build for Netlify serverless deployment
  adapter: netlify()
}
```

--------------------------------

### Astro Pagination Example Component

Source: https://v6.docs.astro.build/en/guides/routing

An Astro component example demonstrating how to use the `page` prop to display current page information and navigation links. It iterates over `page.data` to list items and conditionally renders 'First', 'Previous', 'Next', and 'Last' page links based on the availability of URLs.

```astro
---
// Paginate same list of `{ astronaut }` objects as the previous example
export function getStaticPaths({ paginate }) { /* ... */ }
const { page } = Astro.props;
---
<h1>Page {page.currentPage}</h1>
<ul>
  {page.data.map(({ astronaut }) => <li>{astronaut}</li>)}
</ul>
{page.url.first ? <a href={page.url.first}>First</a> : null}
{page.url.prev ? <a href={page.url.prev}>Previous</a> : null}
{page.url.next ? <a href={page.url.next}>Next</a> : null}
{page.url.last ? <a href={page.url.last}>Last</a> : null}
```

--------------------------------

### Install AWS Amplify Adapter for Astro (npm)

Source: https://v6.docs.astro.build/en/guides/deploy/aws

Installs the community-maintained AWS Amplify adapter for Astro using npm, enabling server-rendered deployments.

```bash
npm install astro-aws-amplify
```

--------------------------------

### Initialize Minimal Astro Project for Demo

Source: https://v6.docs.astro.build/en/reference/publish-to-npm

Create a minimal Astro project to serve as a demo or testing environment for your component. This is useful for integrating and showcasing your component's functionality.

```bash
npm create astro@latest demo -- --template minimal
# yarn
yarn create astro demo --template minimal
# pnpm
pnpm create astro@latest demo -- --template minimal
```

--------------------------------

### Manually Install @astrojs/markdoc Package

Source: https://v6.docs.astro.build/en/guides/integrations-guide/markdoc

Install the @astrojs/markdoc package manually using npm, pnpm, or Yarn. This is an alternative to the automated `astro add` command.

```bash
npm install @astrojs/markdoc

```

```bash
pnpm add @astrojs/markdoc

```

```bash
yarn add @astrojs/markdoc

```

--------------------------------

### Install Wrangler CLI

Source: https://v6.docs.astro.build/en/guides/deploy/cloudflare

Installs the latest version of the Wrangler CLI as a development dependency using npm, pnpm, or Yarn.

```bash
npm install wrangler@latest --save-dev
```

```bash
pnpm add wrangler@latest --save-dev
```

```bash
yarn add wrangler@latest --dev
```

--------------------------------

### Fetch and Render Contentful Blog Posts in Astro

Source: https://v6.docs.astro.build/en/guides/cms/contentful

Fetch blog post data from Contentful using the initialized client and render it within an Astro component. This example demonstrates fetching a 'blogPost' content type and rendering its title and rich text content to HTML.

```astro
---
import { contentfulClient } from "../lib/contentful";
import { documentToHtmlString } from "@contentful/rich-text-html-renderer";
import type { EntryFieldTypes } from "contentful";


interface BlogPost {
  contentTypeId: "blogPost",
  fields: {
    title: EntryFieldTypes.Text
    content: EntryFieldTypes.RichText,
  }
}


const entries = await contentfulClient.getEntries<BlogPost>({
  content_type: "blogPost",
});
---
<body>
  {entries.items.map((item) => (
    <section>
      <h2>{item.fields.title}</h2>
      <article set:html={documentToHtmlString(item.fields.content)}></article>
    </section>
  ))}
</body>
```

--------------------------------

### Manually Install Alpine.js and Types

Source: https://v6.docs.astro.build/en/guides/integrations-guide/alpinejs

Installs Alpine.js and its TypeScript types if they were not automatically installed as peer dependencies. This ensures Alpine.js is available for use.

```bash
npm install alpinejs @types/alpinejs
```

```bash
pnpm add alpinejs @types/alpinejs
```

```bash
yarn add alpinejs @types/alpinejs
```

--------------------------------

### Basic Astro Configuration File Setup

Source: https://v6.docs.astro.build/en/guides/configuring-astro

This snippet demonstrates the basic structure of an Astro configuration file (`astro.config.js`). It uses the `defineConfig` helper from the 'astro/config' module to define project configuration options, providing IntelliSense in IDEs for easier development.

```javascript
import { defineConfig } from "astro/config";


export default defineConfig({
  // your configuration options here...
});
```

--------------------------------

### Install Nano Stores for React

Source: https://v6.docs.astro.build/en/recipes/sharing-state-islands

Installs the Nano Stores library along with its helper package for React. This allows for seamless state sharing between React components in an Astro application.

```bash
npm install nanostores @nanostores/react
```

--------------------------------

### Sign Out User Endpoint (Astro/TypeScript)

Source: https://v6.docs.astro.build/en/guides/backend/supabase

This endpoint handles user sign-out. It accepts GET requests and removes the user's session cookies. Ensure `export const prerender = false;` if using `static` rendering mode.

```typescript
// With `output: 'static'` configured:
// export const prerender = false;
import type { APIRoute } from "astro";


export const GET: APIRoute = async ({ cookies, redirect }) => {
  cookies.delete("sb-access-token", { path: "/" });
  cookies.delete("sb-refresh-token", { path: "/" });
  return redirect("/signin");
};

```

--------------------------------

### Configure Astro with astro.config.mjs

Source: https://v6.docs.astro.build/en/install-and-setup

Creates the astro.config.mjs file at the project root for configuring Astro. This is optional if no custom configuration is needed.

```javascript
import { defineConfig } from "astro/config";


// https://astro.build/config
export default defineConfig({});
```

--------------------------------

### Install Clerk SDK for Astro

Source: https://v6.docs.astro.build/en/guides/authentication

Installs the official Clerk SDK for Astro using various package managers. This is the first step to integrate Clerk's authentication services into your Astro project.

```bash
npm install @clerk/astro
```

```bash
pnpm add @clerk/astro
```

```bash
yarn add @clerk/astro
```

--------------------------------

### Configure Astro for ApostropheCMS Integration

Source: https://v6.docs.astro.build/en/guides/cms/apostrophecms

Configures the `astro.config.mjs` file to integrate ApostropheCMS and Vite. This setup includes specifying the Apostrophe host, mapping widget and template folders, and configuring Vite's server-side rendering with environment variables for communication.

```javascript
import { defineConfig } from 'astro/config';
import node from '@astrojs/node';
import apostrophe from '@apostrophecms/apostrophe-astro';
import { loadEnv } from 'vite';


const env = loadEnv("", process.cwd(), 'APOS');


export default defineConfig({
  output: 'server',
  adapter: node({
    mode: 'standalone'
  }),
  integrations: [
    apostrophe({
      aposHost: 'http://localhost:3000',
      widgetsMapping: './src/widgets',
      templatesMapping: './src/templates'
    })
  ],
  vite: {
    ssr: {
      // Do not externalize the @apostrophecms/apostrophe-astro plugin, we need
      // to be able to use virtual: URLs there
      noExternal: [ '@apostrophecms/apostrophe-astro' ],
    },
    define: {
      'process.env.APOS_EXTERNAL_FRONT_KEY': JSON.stringify(env.APOS_EXTERNAL_FRONT_KEY),
      'process.env.APOS_HOST': JSON.stringify(env.APOS_HOST)
    }
  }
});

```

--------------------------------

### Querying Build-Time Collections

Source: https://v6.docs.astro.build/en/guides/content-collections

Utilize helper functions like `getCollection()` and `getEntry()` to fetch content entries from your defined collections during the build process.

```APIDOC
## Querying Build-Time Collections

### Description
Astro provides helper functions to query build-time collections and retrieve content entries. `getCollection()` fetches all entries from a specified collection, while `getEntry()` fetches a single entry by its ID.

### Method
`getCollection(collectionName)`
`getEntry(collectionName, entryId)`

### Endpoint
N/A (JavaScript functions used in Astro components or setup files)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
import { getCollection, getEntry } from 'astro:content';

// Get all entries from the 'blog' collection
const allBlogPosts = await getCollection('blog');

// Get a single entry with the ID 'poodle' from the 'dogs' collection
const poodleData = await getEntry('dogs', 'poodle');
```

### Response
#### Success Response (CollectionEntry)
Returns an array of `CollectionEntry` objects (for `getCollection`) or a single `CollectionEntry` object (for `getEntry`). Each entry has:
- `id`: A unique identifier for the entry.
- `data`: An object containing all defined frontmatter properties.
- `body`: The raw, uncompiled content of the document.

#### Response Example
```json
{
  "id": "entry-id",
  "data": {
    "title": "Example Title",
    "pubDate": "2023-10-27T10:00:00.000Z"
    // ... other frontmatter properties
  },
  "body": "# Markdown Content\nThis is the body of the entry."
}
```

### Sorting Collection Entries

Collection entries are returned in a non-deterministic order. To ensure a specific sort order, you must sort the results yourself.

### Request Example (Sorting)
```javascript
import { getCollection } from 'astro:content';

const posts = (await getCollection('blog')).sort(
  (a, b) => b.data.pubDate.valueOf() - a.data.pubDate.valueOf(),
);
```
```

--------------------------------

### Install Preact Peer Dependency

Source: https://v6.docs.astro.build/en/guides/integrations-guide/preact

Installs the 'preact' package, which is a peer dependency for @astrojs/preact. This is necessary if your Astro project does not already have Preact installed.

```bash
npm install preact

```

```bash
pnpm add preact

```

```bash
yarn add preact

```

--------------------------------

### Install Sass for Astro

Source: https://v6.docs.astro.build/en/guides/styling

Installs the Sass preprocessor as a project dependency using npm. This allows you to use Sass/SCSS syntax in your Astro components.

```bash
npm install sass

```

--------------------------------

### Create Astro Project from GitHub Repository (Yarn)

Source: https://v6.docs.astro.build/en/install-and-setup

This command creates a new Astro project from a GitHub repository using Yarn. Provide the GitHub username and repository name via the `--template` flag.

```bash
yarn create astro --template <github-username>/<github-repo>
```

--------------------------------

### Build and Deploy to Vercel

Source: https://v6.docs.astro.build/en/guides/integrations-guide/vercel

Commands to build your Astro project locally and deploy it to Vercel using the `--prebuilt` flag. This is a common workflow for deploying Astro sites with the Vercel adapter.

```bash
astro build
vercel deploy --prebuilt
```

--------------------------------

### Install Zephyr Integration Manually (npm, pnpm, Yarn)

Source: https://v6.docs.astro.build/en/guides/deploy/zephyr

Manually installs the Zephyr Astro integration package. This is the first step in the manual installation process.

```bash
npm install zephyr-astro-integration
```

```bash
pnpm add zephyr-astro-integration
```

```bash
yarn add zephyr-astro-integration
```

--------------------------------

### Install PostgreSQL Client for Direct Connection (Node.js)

Source: https://v6.docs.astro.build/en/guides/backend/prisma-postgres

Installs the 'pg' package, a PostgreSQL client for Node.js, to enable direct TCP connections to your Prisma Postgres database. This is used when not employing Prisma ORM.

```bash
npm install pg
```

--------------------------------

### Server-side Data Fetching with Solid.js createResource

Source: https://v6.docs.astro.build/en/guides/integrations-guide/solid-js

Demonstrates fetching asynchronous remote data on the server using Solid's `createResource`. The fetched data is then included in the initial server-rendered HTML by Astro. This example requires the Solid.js library.

```javascript
function CharacterName() {
  const [name] = createResource(() =>
    fetch('https://swapi.dev/api/people/1')
      .then((result) => result.json())
      .then((data) => data.name)
  );


  return (
    <>
      <h2>Name:</h2>
      {/* Luke Skywalker */}
      <div>{name()}</div>
    </>
  );
}
```

--------------------------------

### Integrate Astro Node Handler with Express

Source: https://v6.docs.astro.build/en/guides/integrations-guide/node

This example demonstrates how to use the Astro Node adapter's handler function with an Express application. It shows setting up static file serving for client assets and then using the `ssrHandler` for routing. It also includes an example of passing `Astro.locals` data.

```javascript
import express from 'express';
import { handler as ssrHandler } from './dist/server/entry.mjs';


const app = express();
// Change this based on your astro.config.mjs, `base` option.
// They should match. The default value is "/".
const base = '/';
app.use(base, express.static('dist/client/'));
app.use(ssrHandler);


app.listen(8080);

```

```javascript
import express from 'express';
import { handler as ssrHandler } from './dist/server/entry.mjs';


const app = express();
app.use(express.static('dist/client/'));
app.use((req, res, next) => {
  const locals = {
    title: 'New title',
  };


  ssrHandler(req, res, next, locals);
});


app.listen(8080);

```

--------------------------------

### Install ioredis for Redis Session Storage

Source: https://v6.docs.astro.build/en/guides/integrations-guide/vercel

Install the `ioredis` package to use Redis as a driver for Astro's session storage on Vercel. This is necessary when configuring session options with a Redis URL.

```bash
npm install ioredis
```

```bash
pnpm install ioredis
```

```bash
yarn add ioredis
```

--------------------------------

### Astro Component Composition Example

Source: https://v6.docs.astro.build/en/basics/astro-components

Illustrates component-based design in Astro by showing how a parent component can import and use a 'Button' component multiple times to create a 'ButtonGroup'. This highlights the reusability and composability of Astro components.

```astro
---
import Button from './Button.astro';
---
<div>
  <Button title="Button 1" />
  <Button title="Button 2" />
  <Button title="Button 3" />
</div>

```

--------------------------------

### Initialize Astro Component Template

Source: https://v6.docs.astro.build/en/reference/publish-to-npm

Quickly set up a new Astro component project using one of the provided package managers. This command initializes a new directory with a template specifically designed for Astro components.

```bash
# Initialize the Astro Component template in a new directory
npm create astro@latest my-new-component-directory -- --template component
# yarn
yarn create astro my-new-component-directory --template component
# pnpm
pnpm create astro@latest my-new-component-directory -- --template component
```

--------------------------------

### Astro Build Start Hook

Source: https://v6.docs.astro.build/en/reference/integrations-reference

The `astro:build:start` hook runs after `astro:config:done` and before the production build commences. It's the appropriate place to set up global objects or clients needed during the build process and can also be used to extend adapter API build configuration options.

```typescript
'astro:build:start'?: (options: {
  logger: AstroIntegrationLogger;
}) => void | Promise<void>;
```

--------------------------------

### Manually Install @astrojs/preact Package

Source: https://v6.docs.astro.build/en/guides/integrations-guide/preact

Installs the @astrojs/preact package manually using npm, pnpm, or Yarn. This is an alternative to the automated 'astro add' command.

```bash
npm install @astrojs/preact

```

```bash
pnpm add @astrojs/preact

```

```bash
yarn add @astrojs/preact

```

--------------------------------

### GitHub Actions Deployment for Static Astro Sites

Source: https://v6.docs.astro.build/en/guides/deploy/deno

This GitHub Actions workflow deploys a static Astro site to Deno Deploy. It checks out the repository, installs dependencies using npm, builds the Astro site, and then uploads the 'dist' folder to Deno Deploy. Ensure 'my-deno-project' is replaced with your actual Deno Deploy project name.

```yaml
name: Deploy
on: [push]

jobs:
  deploy:
    name: Deploy
    runs-on: ubuntu-latest
    permissions:
      id-token: write # Needed for auth with Deno Deploy
      contents: read # Needed to clone the repository

    steps:
      - name: Clone repository
        uses: actions/checkout@v4

      # Not using npm? Change `npm ci` to `yarn install` or `pnpm i`
      - name: Install dependencies
        run: npm ci

      # Not using npm? Change `npm run build` to `yarn build` or `pnpm run build`
      - name: Build Astro
        run: npm run build

      - name: Upload to Deno Deploy
        uses: denoland/deployctl@v1
        with:
          project: my-deno-project # TODO: replace with Deno Deploy project name
          entrypoint: jsr:@std/http/file-server
          root: dist
```

--------------------------------

### Manually Install Partytown Package for Astro

Source: https://v6.docs.astro.build/en/guides/integrations-guide/partytown

Installs the Partytown package as a dependency for your Astro project. This is an alternative to the `astro add` command if you prefer manual installation. After installation, you'll need to apply the integration in your configuration file.

```bash
npm install @astrojs/partytown
```

```bash
pnpm add @astrojs/partytown
```

```bash
yarn add @astrojs/partytown
```

--------------------------------

### Astro Script Element Processing (v0.24+)

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

Starting from Astro v0.24, script element processing is opt-in via the `hoist` attribute. The `type="module"` is required for hoisted modules to enable bundling and ESM import resolution.

```html
<script>
  // Will be rendered into the HTML exactly as written!
  // ESM imports will not be resolved relative to the file.
</script>
<script type="module" hoist>
  // Processed! Bundled! ESM imports work, even to npm packages.
</script>
```

--------------------------------

### Example Astro Integration with Middleware Entry Point

Source: https://v6.docs.astro.build/en/reference/integrations-reference

Demonstrates how to define an Astro integration and conditionally perform operations if a middleware entry point is provided during the SSR build.

```javascript
export default {
  name: 'my-integration',
  hooks: {
    'astro:build:ssr': ({ middlewareEntryPoint }) => {
      if (middlewareEntryPoint) {
        // do some operations if a middleware exist
      }
    },
  },
}
```

--------------------------------

### Astro Server Done Hook

Source: https://v6.docs.astro.build/en/reference/integrations-reference

The `astro:server:done` hook is triggered immediately after the development server is closed. It provides a logger instance and is intended for executing any necessary cleanup tasks that were initiated in earlier hooks like `astro:server:setup` or `astro:server:start`.

```typescript
'astro:server:done'?: (options: {
  logger: AstroIntegrationLogger;
}) => void | Promise<void>;
```

--------------------------------

### Display formatted blog post in Astro template

Source: https://v6.docs.astro.build/en/guides/cms/contentful

This Astro code displays a formatted blog post. It fetches and formats the post data as shown in previous examples, then uses the 'post' object to render the title, date, and content within an HTML structure. It includes dependencies for Layout, contentfulClient, documentToHtmlString, and BlogPost type.

```astro
---
import Layout from "../../layouts/Layout.astro";
import { contentfulClient } from "../../lib/contentful";
import { documentToHtmlString } from "@contentful/rich-text-html-renderer";
import type { BlogPost } from "../../lib/contentful";


let post;
const { slug } = Astro.params;
try {
  const data = await contentfulClient.getEntries<BlogPost>({
    content_type: "blogPost",
    "fields.slug": slug,
  });
  const { title, date, content } = data.items[0].fields;
  post = {
    title,
    date: new Date(date).toLocaleDateString(),
    content: documentToHtmlString(content),
  };
} catch (error) {
  return Astro.redirect("/404");
}
---
<html lang="en">
  <head>
    <title>{post?.title}</title>
  </head>
  <body>
    <h1>{post?.title}</h1>
    <time>{post?.date}</time>
    <article set:html={post?.content} />
  </body>
</html>

```

--------------------------------

### Install SolidJS Peer Dependency

Source: https://v6.docs.astro.build/en/guides/integrations-guide/solid-js

Installs the 'solid-js' package, which is a peer dependency for @astrojs/solid-js. This is necessary if Astro warns about not finding the 'solid-js' package.

```bash
npm install solid-js
```

```bash
pnpm add solid-js
```

```bash
yarn add solid-js
```

--------------------------------

### Manually Install @astrojs/vue Package

Source: https://v6.docs.astro.build/en/guides/integrations-guide/vue

Installs the @astrojs/vue package manually using npm, pnpm, or Yarn. This is an alternative to the automated `astro add` command.

```bash
npm install @astrojs/vue
```

```bash
pnpm add @astrojs/vue
```

```bash
yarn add @astrojs/vue
```

--------------------------------

### Install Vite for pnpm

Source: https://v6.docs.astro.build/en/guides/environment-variables

Command to install Vite as a development dependency, necessary when using `pnpm` to utilize the `loadEnv` helper in Astro configuration files.

```bash
pnpm add -D vite
```

--------------------------------

### Install Mux Node SDK

Source: https://v6.docs.astro.build/en/guides/media/mux

Installs the Mux Node SDK using npm, pnpm, or Yarn. This SDK provides authenticated access to the Mux REST API for server-side interactions with Mux assets and data.

```bash
npm install @mux/mux-node
```

```bash
pnpm add @mux/mux-node
```

```bash
yarn add @mux/mux-node
```

--------------------------------

### Minimal Wrangler Configuration for Astro 6

Source: https://v6.docs.astro.build/en/guides/integrations-guide/cloudflare

Provides an example of a minimal `wrangler.jsonc` file for Astro 6 projects. This configuration is sufficient if the project does not require custom bindings or advanced settings, as Astro can automatically generate a default configuration.

```json
{
  "name": "my-astro-app",
}
```

--------------------------------

### Install AWS Amplify Adapter for Astro (pnpm)

Source: https://v6.docs.astro.build/en/guides/deploy/aws

Installs the community-maintained AWS Amplify adapter for Astro using pnpm, enabling server-rendered deployments.

```bash
pnpm add astro-aws-amplify
```

--------------------------------

### Fetch blog post data using slug in Astro

Source: https://v6.docs.astro.build/en/guides/cms/contentful

This snippet demonstrates how to fetch blog post data from Contentful using a dynamic 'slug' parameter in an Astro page. It utilizes Astro.params to get the slug and contentfulClient.getEntries to query the 'blogPost' content type. Dependencies include the contentfulClient and BlogPost type from '../../lib/contentful'.

```astro
---
import { contentfulClient } from "../../lib/contentful";
import type { BlogPost } from "../../lib/contentful";


const { slug } = Astro.params;


const data = await contentfulClient.getEntries<BlogPost>({
  content_type: "blogPost",
  "fields.slug": slug,
});
---
```

--------------------------------

### Add Netlify Adapter for Astro

Source: https://v6.docs.astro.build/en/guides/deploy/netlify

Installs the Netlify adapter for Astro to enable on-demand rendering. This command automatically updates the `astro.config.mjs` file.

```bash
npx astro add netlify
```

--------------------------------

### Configure Node.js Start Script for Astro

Source: https://v6.docs.astro.build/en/guides/deploy/clever-cloud

This script is used for on-demand Node.js Astro applications. It specifies how the Node server should start, listening on all network interfaces (0.0.0.0) and a specific port (8080), which is standard for Clever Cloud applications.

```json
{
  "scripts": {
    "start": "node ./dist/server/entry.mjs --host 0.0.0.0 --port 8080"
  }
}
```

--------------------------------

### Manually Install @astrojs/alpinejs Package

Source: https://v6.docs.astro.build/en/guides/integrations-guide/alpinejs

Installs the @astrojs/alpinejs package and its peer dependencies manually. This is an alternative to the `astro add` command.

```bash
npm install @astrojs/alpinejs
```

```bash
pnpm add @astrojs/alpinejs
```

```bash
yarn add @astrojs/alpinejs
```

--------------------------------

### Preview Built Astro Site Locally

Source: https://v6.docs.astro.build/en/develop-and-build

This command allows you to preview the production-ready version of your Astro site locally after running the build command. This preview reflects the state of your site at the time of the last build and is useful for testing before deployment. Any code changes made after the build will not be reflected until you rebuild.

```bash
npm run preview
```

--------------------------------

### Markdoc Content with Indented Tags Example

Source: https://v6.docs.astro.build/en/guides/integrations-guide/markdoc

This example showcases Markdoc content with arbitrarily indented tags, made possible by enabling the `ignoreIndentation` option. It illustrates how nested custom tags can be indented for improved visual structure and readability. The example highlights that both spaces and tabs can be used for indentation.

```markdoc
# Welcome to Markdoc with indented tags 👋


# Note: Can use either spaces or tabs for indentation

{% custom-tag %}
{% custom-tag %} ### Tags can be indented for better readability

    {% another-custom-tag %}
      This is easier to follow when there is a lot of nesting
    {% /another-custom-tag %}

{% /custom-tag %}
{% /custom-tag %}
```

--------------------------------

### Install Rollup YAML Plugin with npm, pnpm, or Yarn

Source: https://v6.docs.astro.build/en/recipes/add-yaml-support

Installs the `@rollup/plugin-yaml` package as a development dependency using npm, pnpm, or Yarn. This plugin enables the import of YAML files in Astro projects.

```bash
npm install @rollup/plugin-yaml --save-dev
```

```bash
pnpm add @rollup/plugin-yaml --save-dev
```

```bash
yarn add @rollup/plugin-yaml --dev
```

--------------------------------

### Manually install @astrojs/svelte package (npm, pnpm, yarn)

Source: https://v6.docs.astro.build/en/guides/integrations-guide/svelte

Installs the @astrojs/svelte package manually using package managers. This is an alternative to the 'astro add' command.

```bash
npm install @astrojs/svelte

```

```bash
pnpm add @astrojs/svelte

```

```bash
yarn add @astrojs/svelte

```

--------------------------------

### Fetch Hashnode Blog Data with graphql-request (TypeScript)

Source: https://v6.docs.astro.build/en/guides/cms/hashnode

This snippet demonstrates how to set up a GraphQL client and fetch all blog posts or a single post from a Hashnode publication using the graphql-request package. It includes functions for initializing the client, fetching all posts, and fetching a single post by its slug. Dependencies include graphql-request and schema definitions.

```typescript
import { gql, GraphQLClient } from "graphql-request";
import type { AllPostsData, PostData } from "./schema";


export const getClient = () => {
  return new GraphQLClient("https://gql.hashnode.com")
}


const myHashnodeURL = "astroplayground.hashnode.dev";


export const getAllPosts = async () => {
  const client = getClient();


  const allPosts = await client.request<AllPostsData>(
    gql`
      query allPosts {
        publication(host: "${myHashnodeURL}") {
          id
          title
          posts(first: 20) {
            pageInfo{
              hasNextPage
              endCursor
            }
            edges {
              node {
                id
                author{
                  name
                  profilePicture
                }
                title
                subtitle
                brief
                slug
                coverImage {
                  url
                }
                tags {
                  name
                  slug
                }
                publishedAt
                readTimeInMinutes
              }
            }
          }
        }
      }
    `
  );


  return allPosts;
};




export const getPost = async (slug: string) => {
  const client = getClient();


  const data = await client.request<PostData>(
    gql`
      query postDetails($slug: String!) {
        publication(host: "${myHashnodeURL}") {
          id
          post(slug: $slug) {
            id
            author{
              name
              profilePicture
            }
            publishedAt
            title
            subtitle
            readTimeInMinutes
            content{
              html
            }
            tags {
              name
              slug
            }
            coverImage {
              url
            }
          }
        }
      }
    `,
    { slug: slug }
  );


  return data.publication.post;
};

```

--------------------------------

### Install Neon Serverless Driver for Astro

Source: https://v6.docs.astro.build/en/guides/backend/neon

Installs the official Neon serverless driver package using npm. This package provides the necessary functions to interact with the Neon Postgres database from the Astro application.

```bash
npm install @neondatabase/serverless
```

--------------------------------

### Create New Astro Project using Yarn

Source: https://v6.docs.astro.build/en/guides/migrate-to-astro/from-gatsby

Launches the Astro CLI wizard or creates a new project with a specified template using Yarn. This command initializes a new Astro project, allowing for either an interactive setup or a pre-defined starter template.

```bash
# launch the Astro CLI Wizard
yarn create astro@latest


# create a new project with an official example
yarn create astro@latest --template <example-name>
```

--------------------------------

### Install TypeScript for Dev Toolbar Apps (pnpm)

Source: https://v6.docs.astro.build/en/recipes/making-toolbar-apps

Installs TypeScript as a development dependency using pnpm, a required step for compiling JSX code in Astro dev toolbar applications.

```bash
pnpm install --save-dev typescript
```

--------------------------------

### Install Day.js for Time Manipulation (pnpm)

Source: https://v6.docs.astro.build/en/recipes/modified-time

Installs the Day.js library using pnpm, a fast and efficient package manager for Node.js.

```bash
pnpm add dayjs
```

--------------------------------

### Install Astro DB Integration

Source: https://v6.docs.astro.build/en/guides/astro-db

Installs the `@astrojs/db` integration using the `astro add` command. This command is available for npm, pnpm, and Yarn package managers.

```bash
npx astro add db
```

```bash
pnpm astro add db
```

```bash
yarn astro add db
```

--------------------------------

### Astro Server Start Hook

Source: https://v6.docs.astro.build/en/reference/integrations-reference

The `astro:server:start` hook is executed just after the dev server's `listen()` event fires. It provides access to the server's network address information and a logger instance. This hook is suitable for intercepting network requests or performing actions related to the server's network interface.

```typescript
'astro:server:start'?: (options: {
  address: AddressInfo;
  logger: AstroIntegrationLogger;
}) => void | Promise<void>;
```

--------------------------------

### Install AWS Amplify Adapter for Astro (Yarn)

Source: https://v6.docs.astro.build/en/guides/deploy/aws

Installs the community-maintained AWS Amplify adapter for Astro using Yarn, enabling server-rendered deployments.

```bash
yarn add astro-aws-amplify
```

--------------------------------

### Apply remark plugin to Markdown in Astro

Source: https://v6.docs.astro.build/en/guides/markdown-content

This example shows how to apply a custom remark plugin, `exampleRemarkPlugin`, to all Markdown files within an Astro project by configuring the `markdown.remarkPlugins` option in `astro.config.mjs`.

```javascript
import { defineConfig } from 'astro/config';
import { exampleRemarkPlugin } from './example-remark-plugin.mjs';


export default defineConfig({
  markdown: {
    remarkPlugins: [exampleRemarkPlugin]
  },
});
```

--------------------------------

### Install astro-cloudinary with pnpm

Source: https://v6.docs.astro.build/en/guides/media/cloudinary

Installs the Cloudinary Astro SDK using pnpm. This package enables seamless integration of Cloudinary assets within Astro projects.

```bash
pnpm add astro-cloudinary
```

--------------------------------

### Enable Local Development with Azion CLI

Source: https://v6.docs.astro.build/en/guides/deploy/azion

Enables a local development server for your Astro project using the Azion CLI. This command allows you to preview your site locally before deploying, and it includes the build process.

```bash
azion dev
```

--------------------------------

### Astro Code Component with Shiki Transformers

Source: https://v6.docs.astro.build/en/guides/syntax-highlighting

Illustrates how to use Shiki transformers with the Astro `<Code />` component for advanced code highlighting features like meta highlighting and focus. It requires importing specific transformers and provides an example of applying them.

```astro
---
import { transformerNotationFocus, transformerMetaHighlight } from '@shikijs/transformers'
import { Code } from 'astro:components'
const code = `const foo = 'hello'
const bar = ' world'
console.log(foo + bar) // [!code focus] 
`
---
<Code
  code={code}
  lang="js"
  transformers={[transformerMetaHighlight()]}
  meta="{1,3}"
/>


<style is:global>
  pre.has-focused .line:not(.focused) {
    filter: blur(1px);
  }
</style>

```

--------------------------------

### Install astro-cloudinary with npm

Source: https://v6.docs.astro.build/en/guides/media/cloudinary

Installs the Cloudinary Astro SDK using npm. This package provides native Astro components for image, video, and upload functionalities.

```bash
npm install astro-cloudinary
```

--------------------------------

### Install Day.js for Time Manipulation (npm)

Source: https://v6.docs.astro.build/en/recipes/modified-time

Installs the Day.js library using npm, which is a lightweight alternative to Moment.js for date and time formatting and manipulation.

```bash
npm install dayjs
```

--------------------------------

### Build Astro Project with Azion CLI

Source: https://v6.docs.astro.build/en/guides/deploy/azion

Builds your Astro project locally using the Azion CLI. This command compiles your project's assets and code, preparing them for deployment.

```bash
azion build
```

--------------------------------

### Install Day.js for Time Manipulation (Yarn)

Source: https://v6.docs.astro.build/en/recipes/modified-time

Installs the Day.js library using Yarn, a popular package manager for JavaScript.

```bash
yarn add dayjs
```

--------------------------------

### Configure PostCSS with Autoprefixer and CSSnano

Source: https://v6.docs.astro.build/en/guides/styling

This snippet shows how to configure PostCSS for an Astro project by creating a `postcss.config.cjs` file. It demonstrates importing and using plugins like `autoprefixer` and `cssnano` after installing them.

```javascript
module.exports = {
  plugins: [
    require('autoprefixer'),
    require('cssnano'),
  ],
};
```

--------------------------------

### Fetch and Render Blog Posts in Astro

Source: https://v6.docs.astro.build/en/guides/cms/kontent-ai

Fetch blog post content from Kontent.ai using the initialized DeliveryClient and render their titles in an Astro component. This example demonstrates basic content retrieval and display.

```astro
---
import { deliveryClient } from "../lib/kontent";


const blogPosts = await deliveryClient
    .items()
    .type("blogPost")
    .toPromise()
---
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>Astro</title>
  </head>
  <body>
        <ul>
        {blogPosts.data.items.map(blogPost => (
            <li>{blogPost.elements.title.value}</li>
        ))}
        </ul>
    </body>
</html>
```

--------------------------------

### Install Mux Player Astro Package

Source: https://v6.docs.astro.build/en/guides/media/mux

These commands show how to install the Mux Player Astro component using different package managers (npm, pnpm, Yarn). This is a prerequisite for using the MuxPlayer component in your Astro project.

```bash
npm install @mux/mux-player-astro
```

```bash
pnpm add @mux/mux-player-astro
```

```bash
yarn add @mux/mux-player-astro
```

--------------------------------

### Install Nano Stores for Vue

Source: https://v6.docs.astro.build/en/recipes/sharing-state-islands

Installs the Nano Stores library along with its helper package for Vue. This enables the use of Nano Stores for managing and sharing state within Vue components in an Astro application.

```bash
npm install nanostores @nanostores/vue
```

--------------------------------

### Install LightningCSS for Astro

Source: https://v6.docs.astro.build/en/guides/styling

Installs the LightningCSS transformer as a project dependency using npm. This enables faster CSS parsing and transformation within your Astro build process.

```bash
npm install lightningcss

```

--------------------------------

### Fetch Dynamic Content within a Server Island in Astro

Source: https://v6.docs.astro.build/en/guides/server-islands

This example shows how to fetch dynamic data, such as a user's avatar URL, within a server island component in Astro. It accesses cookies to get session information and then uses an asynchronous function to retrieve the avatar. The fetched URL is then used to render an `<img>` tag. This highlights the ability of server islands to perform server-side operations like data fetching and cookie access.

```astro
---\nimport { getUserAvatar } from '../sessions';
const userSession = Astro.cookies.get('session');
const avatarURL = await getUserAvatar(userSession);
---
<img alt="User avatar" src={avatarURL} />

```

--------------------------------

### Importing MDX Files with Astro.glob

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

Demonstrates how to import multiple MDX files using Astro.glob and render them. This replaces older methods of importing markdown content.

```javascript
---
// Multiple imports with Astro.glob
const mdxPosts = await Astro.glob('./posts/*.mdx');
---


<React.Fragment>{mdxPosts.map(Post => <Post.default />)}</React.Fragment>
```

--------------------------------

### Configure Astro Integration in astro.config.js

Source: https://v6.docs.astro.build/en/reference/integrations-reference

After adding your integration to `package.json`, users can configure it in their `astro.config.*` file. This example shows how to import and add a default export integration named 'example'.

```javascript
import { defineConfig } from 'astro/config';
import example from 'example';


export default defineConfig({
  integrations: [example()]
})

```

--------------------------------

### Install Wrangler CLI for Astro

Source: https://v6.docs.astro.build/en/guides/deploy/cloudflare

Installs the latest version of the Wrangler CLI, a tool for building and deploying Cloudflare Workers. This is a development dependency.

```bash
npm install wrangler@latest --save-dev
```

--------------------------------

### Basic Astro Prism Component Usage

Source: https://v6.docs.astro.build/en/guides/syntax-highlighting

Demonstrates the basic usage of the Astro `<Prism />` component for syntax highlighting JavaScript code. It shows how to import the component and pass the language and code as props.

```astro
---
import { Prism } from '@astrojs/prism';
---
<Prism lang="js" code={`const foo = 'bar';`} />

```

--------------------------------

### Turso CLI Commands for Database URL and Token

Source: https://v6.docs.astro.build/en/guides/backend/turso

These commands retrieve the database URL and create an authentication token for your Turso database. The output should be added to your project's .env file.

```bash
turso db show <database-name> --url
turso db tokens create <database-name>
```

--------------------------------

### Install Vue Peer Dependency

Source: https://v6.docs.astro.build/en/guides/integrations-guide/vue

Installs the Vue package as a peer dependency if a 'Cannot find package vue' warning appears. This ensures Vue is available for the integration.

```bash
npm install vue
```

```bash
pnpm add vue
```

```bash
yarn add vue
```

--------------------------------

### Start Astro dev server with remote DB connection

Source: https://v6.docs.astro.build/en/guides/astro-db

This command starts the Astro development server and connects to a remote database. Be cautious as this connects to your live production database, and all changes will be persisted. Ensure necessary environment variables are set for both local development and deployment.

```bash
astro dev --remote
```

--------------------------------

### includeFiles Configuration

Source: https://v6.docs.astro.build/en/guides/integrations-guide/vercel

Force specific files to be bundled with your Serverless function using the `includeFiles` option. This is useful for ensuring all necessary files are included.

```APIDOC
## `includeFiles` Configuration

### Description
Use this property to force files to be bundled with your function. This is helpful when you notice missing files. Available for Serverless deployments.

### Method
Configuration within `astro.config.mjs`

### Endpoint
N/A

### Parameters
#### Path Parameters
N/A

#### Query Parameters
N/A

#### Request Body
N/A

### Request Example
```javascript
import { defineConfig } from 'astro/config';
import vercel from '@astrojs/vercel';


export default defineConfig({
  // ...
  adapter: vercel({
    includeFiles: ['./my-data.json'],
  }),
});
```

### Response
#### Success Response (200)
N/A

#### Response Example
N/A
```

--------------------------------

### Configuring ClientRouter Fallback in Astro

Source: https://v6.docs.astro.build/en/guides/view-transitions

Illustrates how to configure the fallback behavior of the `<ClientRouter />` component in Astro. This example sets the `fallback` property to 'swap', which replaces the old page content immediately without animation, useful for browsers that do not support View Transitions.

```astro
---
import { ClientRouter } from "astro:transitions";
---
<title>My site</title>


<ClientRouter fallback="swap" />

```

--------------------------------

### Install Astro TypeScript Plugin with npm

Source: https://v6.docs.astro.build/en/guides/typescript

This command installs the Astro TypeScript plugin using npm. This plugin enhances editor support for `.astro` files, providing autocompletion, hints, and error checking within your IDE.

```bash
npm install @astrojs/ts-plugin
```

--------------------------------

### Build custom swap function using Astro transition utilities

Source: https://v6.docs.astro.build/en/guides/view-transitions

This example demonstrates building a custom page swap function by utilizing utility functions from 'astro:transitions/client'. It recreates Astro's default swap behavior, including attribute swapping, head element updates, and body replacement.

```javascript
<script>
  import { swapFunctions } from "astro:transitions/client";


  // substitutes `window.document` with `doc`
  function mySwap(doc: Document) {
    swapFunctions.deselectScripts(doc);
    swapFunctions.swapRootAttributes(doc);
    swapFunctions.swapHeadElements(doc);
    const restoreFocusFunction = swapFunctions.saveFocus();
    swapFunctions.swapBodyElement(doc.body, document.body);
    restoreFocusFunction();
  }


  document.addEventListener("astro:before-swap", (event) => {
    event.swap = () => mySwap(event.newDocument);
  });
<script>
```

--------------------------------

### Set Environment Variables for Static Deployment with pnpm

Source: https://v6.docs.astro.build/en/guides/deploy/clever-cloud

Configures the build environment for a static Astro application using pnpm. It sets the post-build hook to run the build command, and the pre-build hook to install pnpm globally, install dependencies, and disable Astro telemetry. The webroot is set to '/dist'.

```bash
CC_POST_BUILD_HOOK="pnpm build"
CC_PRE_BUILD_HOOK="npm install -g pnpm && pnpm install && pnpm run astro telemetry disable"
CC_WEBROOT="/dist"
```

--------------------------------

### astro/app - App Constructor and render()

Source: https://v6.docs.astro.build/en/reference/adapter-reference

The `App` class from `astro/app` is used for rendering prebuilt pages. The `render()` method handles page requests and returns a `Response` object.

```APIDOC
## `astro/app` Module

### Description
This module is used for rendering pages that have been prebuilt through `astro build`. Astro uses the standard `Request` and `Response` objects. Hosts that have a different API for request/response should convert to these types in their adapter.

### `App` Constructor
- **manifest** (SSRManifest) - Required argument for the SSR manifest.
- **options** (object) - Optional argument to enable or disable streaming, defaulting to `true`.

### `app.render(request, options?)`

#### Description
A method that accepts a required `request` argument and an optional `RenderOptions` object. This calls the Astro page that matches the request, renders it, and returns a promise to a `Response` object. This also works for API routes that do not render pages.

#### Method
`(request: Request, options?: RenderOptions) => Promise<Response>`

#### Parameters
##### Path Parameters
None

##### Query Parameters
None

##### Request Body
None

### Request Example
```javascript
import { App } from 'astro/app';
import http from 'http';

export function start(manifest) {
  const app = new App(manifest);

  addEventListener('fetch', event => {
    event.respondWith(
      app.render(event.request)
    );
  });
}
```

### Response
#### Success Response (200)
- **Promise<Response>** - A promise that resolves to a `Response` object.

#### Response Example
```javascript
const response = await app.render(request);
```

### `RenderOptions` Object

#### Description
An object that controls the rendering and contains the following properties:

#### Properties
- **addCookieHeader** (boolean) - Optional. Default: `false`. Whether or not to automatically add all cookies written by `Astro.cookie.set()` to the response headers.
- **clientAddress** (string) - Optional. Default: `request[Symbol.for("astro.clientAddress")]`. The client IP address that will be made available as `Astro.clientAddress`.
- **locals** (object) - Optional. Custom local data.
- **prerenderedErrorPageFetch** (function) - Optional. A function to fetch prerendered error pages.
- **routeData** (object) - Optional. Data for the current route.

### `RenderOptions` Example
```javascript
const clientAddress = request.headers.get("x-forwarded-for");
const response = await app.render(request, { 
  addCookieHeader: true,
  clientAddress: clientAddress 
});
```
```

--------------------------------

### Configure Playwright to Launch Development Server

Source: https://v6.docs.astro.build/en/guides/testing

This configuration allows Playwright to automatically start a development web server when tests are run. It specifies the command to start the server, the URL to access it, a timeout for the server to become available, and an option to reuse an existing server if not running in a CI environment. The baseURL is also set for Playwright's requests.

```typescript
import { defineConfig } from '@playwright/test';


export default defineConfig({
  webServer: {
    command: 'npm run preview',
    url: 'http://localhost:4321/',
    timeout: 120 * 1000,
    reuseExistingServer: !process.env.CI,
  },
  use: {
    baseURL: 'http://localhost:4321/',
  },
});
```

--------------------------------

### Install rollup-plugin-visualizer (npm, pnpm, Yarn)

Source: https://v6.docs.astro.build/en/recipes/analyze-bundle-size

Installs the `rollup-plugin-visualizer` package as a development dependency using npm, pnpm, or Yarn. This package is essential for analyzing your Rollup bundle.

```bash
npm install rollup-plugin-visualizer --save-dev
```

```bash
pnpm add rollup-plugin-visualizer --save-dev
```

```bash
yarn add rollup-plugin-visualizer --save-dev
```

--------------------------------

### Upgrade All Astro Integrations (npm, pnpm, Yarn)

Source: https://v6.docs.astro.build/en/guides/integrations-guide

Commands to upgrade Astro and all official integrations to their latest versions simultaneously using different package managers.

```bash
# Upgrade Astro and official integrations together to latest
npx @astrojs/upgrade
```

```bash
# Upgrade Astro and official integrations together to latest
pnpm dlx @astrojs/upgrade
```

```bash
# Upgrade Astro and official integrations together to latest
yarn dlx @astrojs/upgrade
```

--------------------------------

### Install Mux Video Web Component

Source: https://v6.docs.astro.build/en/guides/media/mux

Installs the Mux video web component using npm, pnpm, or Yarn. This component is a drop-in replacement for the HTML5 <video> element, offering HLS playback and Mux Data integration.

```bash
npm install @mux/mux-video
```

```bash
pnpm add @mux/mux-video
```

```bash
yarn add @mux/mux-video
```

--------------------------------

### Self-Host Astro Application with Environment Variables

Source: https://v6.docs.astro.build/en/guides/integrations-guide/node

This Dockerfile snippet illustrates how to build and run an Astro application in a self-hosted environment. It includes steps for installing dependencies, building the project, and setting environment variables at runtime.

```dockerfile
FROM node:lts AS runtime
WORKDIR /app

COPY . .

RUN npm install
RUN npm run build

ENV DB_HOST=...
ENV DB_PASSWORD=...
CMD node ./dist/server/entry.mjs
```

--------------------------------

### Drupal JSON:API Module Installation

Source: https://v6.docs.astro.build/en/guides/cms/drupal

Instructions on how to enable the JSON:API module in Drupal to allow external data fetching.

```APIDOC
## Enable Drupal JSON:API Module

### Description
Enables the JSON:API module in Drupal to allow external data fetching for your Astro project.

### Steps
1. Navigate to the Extend page (`admin/modules`) via the Manage administrative menu.
2. Locate the JSON:API module and check the box next to it.
3. Click Install to install the new module.
```

--------------------------------

### Build Docker Image for Astro Website

Source: https://v6.docs.astro.build/en/recipes/docker

Builds a Docker image for your Astro website. This command should be run in the project's root directory. The output is a Docker image that can be used for local testing or deployment.

```bash
docker build -t <your-astro-image-name> .
```

--------------------------------

### Install @astrojs/rss package

Source: https://v6.docs.astro.build/en/recipes/rss

Install the @astrojs/rss package using npm, pnpm, or Yarn. This package provides helpers for generating RSS feeds.

```bash
npm install @astrojs/rss
```

```bash
pnpm add @astrojs/rss
```

```bash
yarn add @astrojs/rss
```

--------------------------------

### Replace Astro.canonicalURL with Astro.url

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

Demonstrates how to replace the deprecated `Astro.canonicalURL` with the new `Astro.url` helper for constructing canonical URLs.

```javascript
// Before:
const canonicalURL = ~~Astro.canonicalURL~~
// After:
const canonicalURL = new URL(Astro.url.pathname, Astro.site);
```

--------------------------------

### Install Kontent.ai Delivery SDK for Astro (npm, pnpm, yarn)

Source: https://v6.docs.astro.build/en/guides/cms/kontent-ai

Install the Kontent.ai TypeScript SDK to enable communication between your Astro application and your Kontent.ai project. This SDK provides the necessary tools for fetching content.

```bash
npm install @kontent-ai/delivery-sdk
```

```bash
pnpm add @kontent-ai/delivery-sdk
```

```bash
yarn add @kontent-ai/delivery-sdk
```

--------------------------------

### Configure Google Font Provider with Options

Source: https://v6.docs.astro.build/en/reference/experimental-flags/fonts

This example illustrates configuring the Google font provider with additional options, such as specifying specific glyphs to download for a font family. This allows for more granular control over font assets, potentially improving performance by only including necessary characters.

```javascript
provider: fontProviders.google({
  glyphs: {
    Roboto: ["a"]
  }
})
```

--------------------------------

### Internal Markdown Linking Example

Source: https://v6.docs.astro.build/en/guides/markdown-content

Illustrates how to create internal links within a Markdown file using heading anchors. The example shows linking to a section with the ID 'conclusion' from a section with the heading 'Introduction'.

```markdown
---
title: My page of content
---
## Introduction


I can link internally to [my conclusion](#conclusion) on the same page when writing Markdown.


## Conclusion


I can visit `https://example.com/page-1/#introduction` in a browser to navigate directly to my Introduction.
```

--------------------------------

### Install astro-cloudinary with Yarn

Source: https://v6.docs.astro.build/en/guides/media/cloudinary

Installs the Cloudinary Astro SDK using Yarn. This SDK offers components for optimized image and video delivery, along with upload capabilities.

```bash
yarn add astro-cloudinary
```

--------------------------------

### Install @astrojs/sitemap using npm, pnpm, or yarn

Source: https://v6.docs.astro.build/en/guides/integrations-guide/sitemap

Commands to add the @astrojs/sitemap integration to your Astro project using different package managers.

```bash
npx astro add sitemap

```

```bash
pnpm astro add sitemap

```

```bash
yarn astro add sitemap

```

--------------------------------

### Deploy Astro Site using Azion CLI

Source: https://v6.docs.astro.build/en/guides/deploy/azion

Deploys your static Astro site files using the Azion CLI. After building your project, this command uploads the necessary files to the Azion platform for distribution.

```bash
azion deploy
```

--------------------------------

### Configure MuxPlayer for Video Playback

Source: https://v6.docs.astro.build/en/guides/media/mux

This example demonstrates configuring the MuxPlayer Astro component with various styling and playback options. It includes setting aspect ratio, colors, and enabling remaining time display for a video asset.

```astro
<MuxPlayer
  playbackId="FOTbeIxKeMPzyhrob722wytaTGI02Y3zbV00NeFQbTbK00"
  metadata={{
    video_title: 'Starlight by Astro',
  }}
  style={{
    display: 'block',
    aspectRatio: '16/9',
    backgroundColor: '#000',
    margin: '1rem 0 2rem',
  }}
  primaryColor="#f2ec3a"
  secondaryColor="#0caa09"
  accentColor="#6e1e99"
  defaultShowRemainingTime={true}
/>
```

--------------------------------

### Install TypeScript for Dev Toolbar Apps (npm)

Source: https://v6.docs.astro.build/en/recipes/making-toolbar-apps

Installs TypeScript as a development dependency using npm, which is necessary for compiling JSX code in Astro dev toolbar apps.

```bash
npm install --save-dev typescript
```

--------------------------------

### Install Reading Time Helper Packages (npm)

Source: https://v6.docs.astro.build/en/recipes/reading-time

Installs the 'reading-time' and 'mdast-util-to-string' packages using npm. These packages are essential for calculating reading time and extracting text from Markdown content.

```bash
npm install reading-time mdast-util-to-string
```

--------------------------------

### Import Raw CSS Content in Astro

Source: https://v6.docs.astro.build/en/guides/styling

This advanced example shows how to import CSS content directly from a file using the `?raw` query parameter. This bypasses Astro's bundling and optimization, providing direct access to the CSS string for use in `<style is:inline>` tags. This method is not recommended for most users.

```astro
---
// Advanced example! Not recommended for most users.
import rawStylesCSS from '../styles/main.css?raw';
---
<style is:inline set:html={rawStylesCSS}></style>
```

--------------------------------

### Live Loaders with Cache Hints

Source: https://v6.docs.astro.build/en/reference/content-loader-reference

Example of implementing a live loader that provides cache hints for entries and the collection.

```APIDOC
## Live Loaders with Cache Hints

### Description
Live loaders can provide cache hints to help with response caching. This data can be used to send HTTP cache headers or inform your caching strategy.

### Method
N/A (Loader implementation)

### Endpoint
N/A (Loader implementation)

### Parameters
N/A

### Request Example
```javascript
import type { LiveLoader } from "astro/loaders";
import { loadStoreProduct, loadStoreProducts, getLastModifiedDate } from "./store";
import type { Product, ProductEntryFilter, ProductCollectionFilter } from "./types";


export function myLoader(config): LiveLoader<Product, ProductEntryFilter, ProductCollectionFilter> {
  return {
    name: 'cached-loader',
    loadCollection: async ({ filter }) => {
      const products = await loadStoreProducts(filter);
      return {
        entries: products.map((item) => ({
          id: item.id,
          data: item,
          // You can optionally provide cache hints for each entry
          cacheHint: {
            tags: [`product-${item.id}`, `category-${item.category}`],
          },
        })),
        cacheHint: {
          // All fields are optional, and are combined with each entry's cache hints
          // tags are merged from all entries
          // lastModified is the most recent lastModified of all entries and the collection
          lastModified: getLastModifiedDate(products),
          tags: ['products'],
        },
      };
    },
    loadEntry: async ({ filter }) => {
      const item = await loadStoreProduct(filter);
      return {
        id: item.id,
        data: item,
        cacheHint: {
          lastModified: new Date(item.lastModified),
          tags: [`product-${item.id}`, `category-${item.category}`],
        },
      };
    },
  };
}
```

### Response
#### Success Response (N/A - Loader Output)
- **entries** (Array<Object>) - An array of collection entries, each potentially with a `cacheHint` object.
- **cacheHint** (Object) - Cache hints for the collection, including `tags` (Array<string>) and `lastModified` (Date).

#### Response Example (Collection Output)
```json
{
  "entries": [
    {
      "id": "1",
      "data": { ... },
      "cacheHint": {
        "tags": ["product-1", "category-electronics"],
        "lastModified": "2023-10-27T10:00:00Z"
      }
    }
  ],
  "cacheHint": {
    "tags": ["products", "product-1", "category-electronics"],
    "lastModified": "2023-10-27T10:00:00Z"
  }
}
```

#### Success Response (N/A - Entry Output)
- **id** (string) - The unique identifier for the entry.
- **data** (Object) - The data for the entry.
- **cacheHint** (Object) - Cache hints for the entry, including `tags` (Array<string>) and `lastModified` (Date).

#### Response Example (Entry Output)
```json
{
  "id": "1",
  "data": { ... },
  "cacheHint": {
    "lastModified": "2023-10-27T10:00:00Z",
    "tags": ["product-1", "category-electronics"]
  }
}
```
```

--------------------------------

### Install TypeScript for Dev Toolbar Apps (Yarn)

Source: https://v6.docs.astro.build/en/recipes/making-toolbar-apps

Installs TypeScript as a development dependency using Yarn, essential for compiling JSX code within Astro dev toolbar apps.

```bash
yarn add --dev typescript
```

--------------------------------

### Install CloudCannon Editable Regions Package

Source: https://v6.docs.astro.build/en/guides/cms/cloudcannon

Installs the necessary package for enabling CloudCannon's Component Editable Regions in Astro projects. It provides commands for npm, pnpm, and Yarn package managers.

```bash
npm install @cloudcannon/editable-regions
```

```bash
pnpm add @cloudcannon/editable-regions
```

```bash
yarn add @cloudcannon/editable-regions
```

--------------------------------

### Importing a Single MDX File

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

Shows how to import a single MDX file and use its default export as a component. This is useful for individual pages or components written in MDX.

```javascript
---
// Import a single page
import { default as About } from './about.mdx';
---


<About />
```

--------------------------------

### Configure Custom Entrypoint Type and Rollup Options

Source: https://v6.docs.astro.build/en/reference/adapter-reference

Specifies whether Astro automatically creates the adapter's entrypoint or if a custom one is used. This example configures `entryType: "self"` and sets `rollupOptions.input` to a custom entrypoint path.

```javascript
export default function createIntegration() {
  return {
    name: '@example/my-adapter',
    hooks: {
      'astro:config:setup': ({ updateConfig }) => {
        updateConfig({
          vite: {
            build: {
              rollupOptions: {
                input: "@example/my-adapter/custom-entrypoint.js"
              }
            }
          }
        })
      },
      'astro:config:done': ({ setAdapter }) => {
        setAdapter({
          name: '@example/my-adapter',
          serverEntrypoint: '@example/my-adapter/server.js',
          entryType: "self",
        });
      },
    },
  };
}
```

--------------------------------

### Run Astro Site Preview with Bun

Source: https://v6.docs.astro.build/en/recipes/bun

Previews the production build of your Astro site locally using Bun. This command is typically run after the build process to verify the deployed version.

```bash
bun run preview
```

--------------------------------

### Create Astro Project with React and Partytown (Yarn)

Source: https://v6.docs.astro.build/en/install-and-setup

This command creates a new Astro project and adds React and Partytown integrations using Yarn. The `--add` flag is used to specify the integrations.

```bash
yarn create astro --add react --add partytown
```

--------------------------------

### Install JSON:API Dependencies for Astro (npm)

Source: https://v6.docs.astro.build/en/guides/cms/drupal

Install the 'jsona' and 'drupal-jsonapi-params' npm packages to simplify handling complex JSON:API requests and responses within your Astro project. These packages help serialize/deserialize data and build optimized queries.

```bash
npm install jsona drupal-jsonapi-params

```

--------------------------------

### Astro .dockerignore file example

Source: https://v6.docs.astro.build/en/recipes/docker

This .dockerignore file specifies files and directories that should be excluded from the Docker build context. This helps to speed up the build process and reduce the size of the final Docker image by preventing unnecessary files from being copied.

```ignore
.DS_Store
node_modules
dist
```

--------------------------------

### Install Svelte and TypeScript peer dependencies (npm, pnpm, yarn)

Source: https://v6.docs.astro.build/en/guides/integrations-guide/svelte

Installs Svelte and TypeScript, which are required peer dependencies for the @astrojs/svelte integration. This step is necessary if warnings about missing packages appear.

```bash
npm install svelte typescript

```

```bash
pnpm add svelte typescript

```

```bash
yarn add svelte typescript

```

--------------------------------

### Enable Solid DevTools in Astro

Source: https://v6.docs.astro.build/en/guides/integrations-guide/solid-js

Installs the 'solid-devtools' package and configures the SolidJS integration to enable Solid DevTools during development. This requires passing `devtools: true` to the integration config.

```bash
npm install solid-devtools
```

```bash
pnpm add solid-devtools
```

```bash
yarn add solid-devtools
```

--------------------------------

### Configure Standalone Server Host and Port

Source: https://v6.docs.astro.build/en/guides/integrations-guide/node

This example shows how to override the default host and port for the standalone Astro Node adapter server. By setting the `HOST` and `PORT` environment variables before running the server entrypoint, you can control the network interface and port the server listens on.

```bash
HOST=0.0.0.0 PORT=4321 node ./dist/server/entry.mjs

```

--------------------------------

### Add Astro Node.js Adapter (npm, pnpm, Yarn)

Source: https://v6.docs.astro.build/en/guides/deploy/seenode

Installs the Node.js adapter for Astro, enabling server-side rendering. This command modifies your project to include the necessary adapter for deployment.

```bash
npx astro add node
```

```bash
pnpm astro add node
```

```bash
yarn astro add node
```

--------------------------------

### Applying Cache Hints in Pages

Source: https://v6.docs.astro.build/en/reference/content-loader-reference

Example of how to consume cache hints from a live loader and apply them to Astro response headers.

```APIDOC
## Applying Cache Hints in Pages

### Description
This example demonstrates how to use the `getLiveEntry` function to fetch data and its associated cache hints, and then apply these hints to the response headers.

### Method
N/A (Page script)

### Endpoint
N/A (Page script)

### Parameters
#### Path Parameters
- **id** (string) - Required - The ID of the entry to fetch.

### Request Example
```astro
---
export const prerender = false; // Not needed in 'server' mode


import { getLiveEntry } from 'astro:content';


const { entry, error, cacheHint } = await getLiveEntry('products', Astro.params.id);


if (error) {
  return Astro.redirect('/404');
}


// Apply cache hints to response headers
if (cacheHint?.tags) {
  Astro.response.headers.set('Cache-Tag', cacheHint.tags.join(','));
}


if (cacheHint?.lastModified) {
  Astro.response.headers.set('Last-Modified', cacheHint.lastModified.toUTCString());
}
---


<h1>{entry.data.name}</h1>
<p>{entry.data.description}</p>
```

### Response
#### Success Response (200)
- **entry** (Object) - The fetched entry data, including `data` and potentially `cacheHint`.
- **error** (any) - An error object if fetching fails.
- **cacheHint** (Object) - Cache hints provided by the loader, containing `tags` and `lastModified`.

#### Response Example
```html
<!-- HTML content rendered from entry.data -->
<h1>Example Product</h1>
<p>This is an example product description.</p>
```
```

--------------------------------

### Install Tailwind Typography with pnpm

Source: https://v6.docs.astro.build/en/recipes/tailwind-rendered-markdown

Installs the `@tailwindcss/typography` package as a development dependency using pnpm. This command ensures the necessary plugin is available for your Astro project.

```bash
pnpm add -D @tailwindcss/typography
```

--------------------------------

### Install Reading Time Helper Packages (Yarn)

Source: https://v6.docs.astro.build/en/recipes/reading-time

Installs the 'reading-time' and 'mdast-util-to-string' packages using Yarn. These packages are essential for calculating reading time and extracting text from Markdown content.

```bash
yarn add reading-time mdast-util-to-string
```

--------------------------------

### Build Astro Site (npm)

Source: https://v6.docs.astro.build/en/guides/deploy/deno

Builds the Astro project for production using npm. This command generates the static or server-rendered output in the `dist` directory.

```bash
npm run build
```

--------------------------------

### Install Reading Time Helper Packages (pnpm)

Source: https://v6.docs.astro.build/en/recipes/reading-time

Installs the 'reading-time' and 'mdast-util-to-string' packages using pnpm. These packages are essential for calculating reading time and extracting text from Markdown content.

```bash
pnpm add reading-time mdast-util-to-string
```

--------------------------------

### Route Pattern Regex Example

Source: https://v6.docs.astro.build/en/reference/integrations-reference

The `pattern` property provides a regular expression used to match an input URL against a specific route. This is crucial for routing logic, allowing Astro to determine the correct page for a given URL. The example shows how a dynamic route like `[fruit]/about.astro` is converted into a regex for matching.

```regex
/^\/([^\/]+?)\/about\/?$/
```

--------------------------------

### SCSS Pre-processor Support in Astro

Source: https://v6.docs.astro.build/en/guides/migrate-to-astro/from-nuxtjs

Illustrates how to enable SCSS support in Astro by installing `sass` as a dev dependency. Once installed, you can use `.scss` or `.sass` syntax directly within Astro's `<style>` tags, including features like nesting and variables.

```bash
npm install -D sass
```

```astro
<p>Hello, world</p>
<style lang="scss">
p {
   color: black;


   &:hover {
       color: red;
   }
}
</style>
```

--------------------------------

### Configure Prettier for Astro Files

Source: https://v6.docs.astro.build/en/editor-setup

Sets up a `.prettierrc` configuration file to include the Astro Prettier plugin and specify the parser for `.astro` files. This ensures Prettier correctly formats Astro syntax.

```json
{
  "plugins": ["prettier-plugin-astro"],
  "overrides": [
    {
      "files": "*.astro",
      "options": {
        "parser": "astro"
      }
    }
  ]
}
```

--------------------------------

### Applying Transitions with Astro Components

Source: https://v6.docs.astro.build/en/guides/view-transitions

Shows how to apply transition animations to elements within Astro components. This example uses the `transition:animate` directive on a `<title>` tag to apply a 'fade' animation, ensuring a consistent visual experience across browsers.

```astro
---
import Layout from "../layouts/LayoutUsingClientRouter.astro";
---
<title transition:animate="fade">About my site</title>

```

--------------------------------

### Configure an in-memory embedded replica

Source: https://v6.docs.astro.build/en/guides/astro-db

This example shows how to set up an in-memory embedded replica of a remote database using the `syncUrl` parameter in the `ASTRO_DB_REMOTE_URL` environment variable. Writes are sent to the remote database and synchronized locally.

```env
ASTRO_DB_REMOTE_URL=memory:?syncUrl=libsql%3A%2F%2Fyour.server.io
```

--------------------------------

### Install JSON:API Dependencies for Astro (pnpm)

Source: https://v6.docs.astro.build/en/guides/cms/drupal

Install the 'jsona' and 'drupal-jsonapi-params' pnpm packages to streamline JSON:API data handling in your Astro project. These tools aid in data serialization/deserialization and query optimization.

```bash
pnpm add jsona drupal-jsonapi-params

```

--------------------------------

### Create Astro Project with Toolbar App Template

Source: https://v6.docs.astro.build/en/recipes/making-toolbar-apps

Use the Astro CLI to quickly scaffold a new Astro project pre-configured with a dev toolbar app template. This is a fast way to start building your custom app.

```bash
npm create astro@latest -- --template toolbar-app
```

```bash
pnpm create astro -- --template toolbar-app
```

```bash
yarn create astro -- --template toolbar-app
```

--------------------------------

### Define Content Collections with Glob Loader

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v6

Example of defining a content collection using Astro's glob loader. This is necessary if your collection does not define a loader, ensuring proper loading of collection entries.

```javascript
import { defineCollection } from 'astro:content';
import { z } from 'astro/zod';
import { glob } from 'astro/loaders';


const blog = defineCollection({
  loader: glob({ pattern: '**/[^_]*.{md,mdx}', base: "./src/data/blog" }),
  schema: z.object({
    title: z.string(),
    description: z.string(),
    pubDate: z.coerce.date(),
    updatedDate: z.coerce.date().optional(),
  }),
});
```

--------------------------------

### Install Tailwind 3 and @astrojs/tailwind Integration

Source: https://v6.docs.astro.build/en/guides/styling

Installs Tailwind CSS version 3 and the official Astro Tailwind integration (`@astrojs/tailwind`) for legacy support. This is used for projects that need to maintain compatibility with Tailwind 3.

```bash
npm install tailwindcss@3 @astrojs/tailwind

```

```bash
pnpm add tailwindcss@3 @astrojs/tailwind

```

```bash
yarn add tailwindcss@3 @astrojs/tailwind

```

--------------------------------

### Set Environment Variables for Node.js Deployment with pnpm

Source: https://v6.docs.astro.build/en/guides/deploy/clever-cloud

Configures the build environment for a Node.js Astro application using pnpm. It sets the build tool to 'custom' and defines pre-build hooks to install pnpm globally, install dependencies with pnpm, and then build the project.

```bash
CC_NODE_BUILD_TOOL="custom"
CC_PRE_BUILD_HOOK="npm install -g pnpm && pnpm install"
CC_CUSTOM_BUILD_TOOL="pnpm run astro telemetry disable && pnpm build"
```

--------------------------------

### Install rehype-external-links Plugin

Source: https://v6.docs.astro.build/en/recipes/external-links

Install the rehype-external-links plugin using your preferred package manager (npm, pnpm, or Yarn). This is the first step to enabling the plugin's functionality.

```npm
npm install rehype-external-links
```

```pnpm
pnpm add rehype-external-links
```

```yarn
yarn add rehype-external-links
```

--------------------------------

### Get Entry from DataStore with get() in JavaScript

Source: https://v6.docs.astro.build/en/reference/content-loader-reference

The `store.get(key)` method retrieves a `DataEntry` from the collection's key-value store by its ID. It returns `undefined` if no entry with the specified key exists.

```javascript
const existingEntry = store.get("my-entry");

```

--------------------------------

### Configure Asset Query Parameters with URLSearchParams

Source: https://v6.docs.astro.build/en/reference/adapter-reference

Defines query parameters to append to all asset URLs. Useful for adapters tracking deployment versions or metadata. This example retrieves a DEPLOY_ID from environment variables and adds it as a custom search parameter.

```javascript
export default function createIntegration() {
  return {
    name: '@example/my-adapter',
    hooks: {
      'astro:config:done': ({ config, setAdapter }) => {
        setAdapter({
          name: '@example/my-adapter',
          serverEntrypoint: '@example/my-adapter/server.js',
          client: {
            assetQueryParams: process.env.DEPLOY_ID
              ? new URLSearchParams({ yourParam: process.env.DEPLOY_ID })
              : undefined,
          },
        });
      },
    },
  };
}
```

--------------------------------

### Configure Development Image Service with Astro Vercel Adapter

Source: https://v6.docs.astro.build/en/guides/integrations-guide/vercel

Allows configuration of the image service used in development with the Vercel adapter. Useful when Sharp dependencies cannot be installed locally, enabling previewing images in the dev environment. Build output remains unaffected.

```javascript
import { defineConfig } from 'astro/config';
import vercel from '@astrojs/vercel';


export default defineConfig({
  // ...
  adapter: vercel({
    imageService: true,
    devImageService: 'sharp',
  }),
});
```

--------------------------------

### Install Cloudinary Node.js SDK in Astro

Source: https://v6.docs.astro.build/en/guides/media/cloudinary

Provides commands to install the Cloudinary Node.js SDK using different package managers (npm, pnpm, Yarn). This SDK is used for more complex asset management tasks within an Astro Node.js environment.

```bash
npm install cloudinary

```

```bash
pnpm add cloudinary

```

```bash
yarn add cloudinary

```

--------------------------------

### Using Glob Patterns

Source: https://v6.docs.astro.build/en/guides/integrations-guide/netlify

Both `includeFiles` and `excludeFiles` support glob patterns for matching multiple files.

```APIDOC
## POST /websites/v6_astro_build_en/glob_patterns

### Description
Supports glob patterns for both `includeFiles` and `excludeFiles` options, allowing for flexible matching of multiple files.

### Method
POST

### Endpoint
/websites/v6_astro_build_en/glob_patterns

### Parameters
#### Request Body
- **includeFiles** (string[]) - Optional - An array of glob patterns for files to include.
- **excludeFiles** (string[]) - Optional - An array of glob patterns for files to exclude.

### Request Example
```json
{
  "includeFiles": ["./data/**/*.json"],
  "excludeFiles": ["./node_modules/package/**/*", "./src/**/*.test.js"]
}
```

### Response
#### Success Response (200)
- **message** (string) - Confirmation message.

#### Response Example
```json
{
  "message": "Glob patterns processed successfully."
}
```
```

--------------------------------

### Update View Transitions Component Import Source

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v3

This example demonstrates updating the import source for the `<ViewTransitions />` component from `astro:components` to `astro:transitions`. This change is necessary for Astro v3.0.

```html
---
import { ViewTransitions } from "astro:transitions"
---
<html lang="en">
  <head>
    <title>My Homepage</title>
    <ViewTransitions />
  </head>
  <body>
    <h1>Welcome to my website!</h1>
  </body>
</html>
```

--------------------------------

### Fetch and Display Blog Posts in Astro

Source: https://v6.docs.astro.build/en/guides/cms/preprcms

This Astro component demonstrates how to fetch blog articles using the Prepr API and display them as a list of links. It imports the Prepr fetching function and the GraphQL query, then iterates over the fetched articles to render the titles and slugs.

```astro
---
import Layout from '../layouts/Layout.astro';
import { Prepr } from '../lib/prepr.js';
import GetArticles from '../queries/get-articles.js';


const response = await Prepr(GetArticles)
const { data } = await response.json()
const articles = data.Articles
---


<Layout title="My blog site">
  <h1>
    My blog site
  </h1>
  <ul>
    {
      articles.items.map((post) => (
        <li>
          <a href={post._slug}>{post.title}</a>
        </li>
      ))
    }
  </ul>
</Layout>
```

--------------------------------

### Install Astro TypeScript Plugin with Yarn

Source: https://v6.docs.astro.build/en/guides/typescript

This command installs the Astro TypeScript plugin using Yarn. This package manager command ensures the TypeScript plugin is added to your project, facilitating better integration with your editor.

```bash
yarn add @astrojs/ts-plugin
```

--------------------------------

### CSS Specificity Example in Astro

Source: https://v6.docs.astro.build/en/guides/styling

Demonstrates how CSS specificity determines style precedence in Astro. More specific rules override less specific ones, regardless of their order.

```html
<style>
  h1 { color: red }
  div > h1 {
    color: purple
  }
</style>
<div>
  <h1>
    This header will be purple!
  </h1>
</div>
```

--------------------------------

### Combining MD and MDX Imports with Astro.glob

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

Illustrates how to import both Markdown (.md) and MDX (.mdx) files using Astro.glob and combine them into a single array. This is helpful during migration.

```javascript
---
const mdPosts = await Astro.glob('../pages/posts/*.md');
const mdxPosts = await Astro.glob('../pages/posts/*.mdx');
const allPosts = [...mdxPosts, ...mdPosts];
---
```

--------------------------------

### Pass Props to Astro Component

Source: https://v6.docs.astro.build/en/tutorial/3-components/2

This example demonstrates how to pass values as props to an Astro component. It shows the JSX-like syntax used within an Astro file to instantiate a component and provide its properties.

```astro
<BlogPost title="My First Post" author="Dan" date="12 Aug 2022" />
```

--------------------------------

### Query Xata Data in an Astro Component

Source: https://v6.docs.astro.build/en/guides/backend/xata

Demonstrates how to import and use the XataClient within an Astro `.astro` file to fetch and display data. It shows initializing the client with environment variables and paginating records.

```astro
---
import { XataClient } from '../../xata';


const xata = new XataClient({
  apiKey: import.meta.env.XATA_API_KEY,
  branch: import.meta.env.XATA_BRANCH
});


const { records } = await xata.db.Posts.getPaginated({
  pagination: {
    size: 50
  }
})
---


<ul>
  {records.map((post) => (
    <li>{post.title}</li>
  ))}
</ul>
```

--------------------------------

### Build On-Demand Routes at Request Time in Astro

Source: https://v6.docs.astro.build/en/guides/content-collections

Enable on-demand rendering with an adapter to generate dynamic page routes at request time. Examine the request parameters to get the slug, then fetch the entry using `getEntry()` or `getLiveEntry()`. The fetched entry is then rendered into HTML.

```astro
---
export const prerender = false; // Not needed in 'server' mode


import { getEntry, render } from "astro:content";


// 1. Get the slug from the incoming server request
const { id } = Astro.params;
if (id === undefined) {
  return Astro.redirect("/404");
}


// 2. Query for the entry directly using the request slug
const post = await getEntry("blog", id);


// 3. Redirect if the entry does not exist
if (post === undefined) {
  return Astro.redirect("/404");
}


// 4. Render the entry to HTML in the template
const { Content } = await render(post);
---
<h1>{post.data.title}</h1>
<Content />

```

--------------------------------

### Configure MDX Integration with Plugins - Astro

Source: https://v6.docs.astro.build/en/guides/integrations-guide/mdx

Provides an example of configuring the MDX integration in Astro, including options for syntax highlighting, remark plugins, rehype plugins, and remark-rehype settings.

```javascript
import { defineConfig } from 'astro/config';
import mdx from '@astrojs/mdx';
import remarkToc from 'remark-toc';
import rehypePresetMinify from 'rehype-preset-minify';


export default defineConfig({
  // ...
  integrations: [
    mdx({
      syntaxHighlight: 'shiki',
      shikiConfig: { theme: 'dracula' },
      remarkPlugins: [remarkToc],
      rehypePlugins: [rehypePresetMinify],
      remarkRehype: { footnoteLabel: 'Footnotes' },
      gfm: false,
    }),
  ],
});

```

--------------------------------

### Astro Features and Adapter Support

Source: https://v6.docs.astro.build/en/reference/adapter-reference

Details how adapters communicate their support for Astro features, such as image services and output formats, and provides examples of configuration.

```APIDOC
## Astro Features and Adapter Support

### Description
Astro features allow adapters to declare their support for specific functionalities. Astro then performs validation and provides contextual logging based on this declared support.

### Supported Astro Features
This object contains configurable features that an adapter can declare support for:

*   **`sharpImageService`** (`'supported' | 'experimental' | 'limited' | 'unsupported'` or `{ support: AdapterSupport; message?: string; }`)
    Defines the adapter's support level for the Sharp-powered built-in image service.

*   **`staticOutput`** (`AdapterSupport`)
    Defines whether the adapter is able to serve static pages.

*   **`hybridOutput`** (`AdapterSupport`)
    Defines whether the adapter is able to serve sites that include a mix of static and on-demand rendered pages.

*   **`serverOutput`** (`AdapterSupport`)
    Defines whether the adapter is able to serve on-demand rendered pages.

*   **`i18nDomains`** (`AdapterSupport`)
    Defines whether the adapter is able to support i18n domains. (Added in `astro@4.3.0`)

### AdapterSupport Type
Represents the level of support for a feature. Possible values include:
*   `'supported'`
*   `'experimental'`
*   `'limited'`
*   `'unsupported'`

### Request Example (Configuring `sharpImageService`)
```javascript
export default function createIntegration() {
  return {
    name: '@example/my-adapter',
    hooks: {
      'astro:config:done': ({ setAdapter }) => {
        setAdapter({
          name: '@example/my-adapter',
          serverEntrypoint: '@example/my-adapter/server.js',
          supportedAstroFeatures: {
            sharpImageService: 'experimental'
          }
        });
      },
    },
  };
}
```

### Request Example (Configuring `sharpImageService` with a message)
```javascript
export default function createIntegration() {
  return {
    name: '@example/my-adapter',
    hooks: {
      'astro:config:done': ({ setAdapter }) => {
        setAdapter({
          name: '@example/my-adapter',
          serverEntrypoint: '@example/my-adapter/server.js',
          supportedAstroFeatures: {
            sharpImageService: {
              support: 'limited',
              message: 'This adapter has limited support for Sharp. Certain features may not work as expected.'
            }
          }
        });
      },
    },
  };
}
```

### Response
N/A (This section describes configuration, not an API endpoint response.)
```

--------------------------------

### Fetch Blog Posts with getCollection in Astro

Source: https://v6.docs.astro.build/en/tutorial/6-islands/4

Demonstrates how to import and use the `getCollection` function from `astro:content` to fetch all blog posts. It then processes the posts to extract unique tags, utilizing `Set` for deduplication and `flat()` to handle potential nested tag arrays.

```astro
import { getCollection } from "astro:content";
import BaseLayout from "../../layouts/BaseLayout.astro";
const allPosts = await getCollection("blog");
const tags = [...new Set(allPosts.map((post) => post.data.tags).flat())];
const pageTitle = "Tag Index";

```

--------------------------------

### Toggle Astro Integration

Source: https://v6.docs.astro.build/en/guides/integrations-guide

Demonstrates how to conditionally include an integration based on a platform check. Falsy values are ignored, allowing for easy toggling.

```javascript
integrations: [
  // Example: Skip building a sitemap on Windows
  process.platform !== 'win32' && sitemap()
]
```

--------------------------------

### Install Specific Astro and Integration Versions (pnpm)

Source: https://v6.docs.astro.build/en/upgrade-astro

Installs a specific version of Astro (4.5.3) and the Astro React integration (3.0.10) using pnpm. This command ensures precise version control for project dependencies.

```bash
pnpm add astro@4.5.3 @astrojs/react@3.0.10
```

--------------------------------

### Basic Astro Code Component Usage with Shiki

Source: https://v6.docs.astro.build/en/guides/syntax-highlighting

Demonstrates the basic usage of the Astro `<Code />` component for syntax highlighting JavaScript code. It shows how to pass code and language, customize themes, enable word wrapping, render inline code, and control default colors.

```astro
---
import { Code } from 'astro:components';
---
<!-- Syntax highlight some JavaScript code. -->
<Code code={`const foo = 'bar';`} lang="js" />
<!-- Optional: Customize your theme. -->
<Code code={`const foo = 'bar';`} lang="js" theme="dark-plus" />
<!-- Optional: Enable word wrapping. -->
<Code code={`const foo = 'bar';`} lang="js" wrap />
<!-- Optional: Output inline code. -->
<p>
  <Code code={`const foo = 'bar';`} lang="js" inline />
  will be rendered inline.
</p>
<!-- Optional: defaultColor -->
<Code code={`const foo = 'bar';`} lang="js" defaultColor={false} />

```

--------------------------------

### Using Props

Source: https://v6.docs.astro.build/en/reference/api-reference

Demonstrates how to access and use props passed to Astro components and from `getStaticPaths()`.

```APIDOC
## Using Props

### Description
The `props` object allows you to pass data into Astro components and access data returned from `getStaticPaths()` for static routes.

### Example 1: Component Props
```astro
---
const { title, date } = Astro.props;
---
<div>
  <h1>{title}</h1>
  <p>{date}</p>
</div>
```

### Example 2: Using Props with getStaticPaths
```astro
---
export function getStaticPaths() {
  return [
    { params: { id: '1' }, props: { author: 'Blu' } },
    { params: { id: '2' }, props: { author: 'Erika' } },
    { params: { id: '3' }, props: { author: 'Matthew' } }
  ];
}

const { id } = Astro.params;
const { author } = Astro.props;
---
```

### Example 3: Endpoint Function with Props
```astro
---
import type { APIContext } from 'astro';

export function getStaticPaths() {
  return [
    { params: { id: '1' }, props: { author: 'Blu' } },
    { params: { id: '2' }, props: { author: 'Erika' } },
    { params: { id: '3' }, props: { author: 'Matthew' } }
  ];
}

export function GET({ props }: APIContext) {
  return new Response(
    JSON.stringify({ author: props.author }),
  );
}
```
```

--------------------------------

### Render Blog Post List Preview (Astro/HTML)

Source: https://v6.docs.astro.build/en/guides/cms/contentful

Renders a list of blog post previews using the `posts` array. Each post includes a link to its individual page, title, publication date, and description.

```astro
---
import { contentfulClient } from "../lib/contentful";
import type { BlogPost } from "../lib/contentful";


const entries = await contentfulClient.getEntries<BlogPost>({
  content_type: "blogPost",
});


const posts = entries.items.map((item) => {
  const { title, date, description, slug } = item.fields;
  return {
    title,
    slug,
    description,
    date: new Date(date).toLocaleDateString()
  };
});
---
<html lang="en">
  <head>
    <title>My Blog</title>
  </head>
  <body>
    <h1>My Blog</h1>
    <ul>
      {posts.map((post) => (
        <li>
          <a href={`/posts/${post.slug}/`}>
            <h2>{post.title}</h2>
          </a>
          <time>{post.date}</time>
          <p>{post.description}</p>
        </li>
      ))}
    </ul>
  </body>
</html>

```

--------------------------------

### Get Static Paths for Blog Posts in Astro

Source: https://v6.docs.astro.build/en/guides/cms/kontent-ai

Exports an async function `getStaticPaths` to enable Static Site Generation (SSG) for individual blog posts in Astro. It fetches all blog posts from Kontent.ai and returns an array of objects, each containing `params` with the `slug` and `props` with the blog post data.

```astro
---
import { deliveryClient } from '../../lib/kontent';
import type { BlogPost } from '../../models';
import { contentTypes } from '../../models/project/contentTypes';


export async function getStaticPaths() {
    const blogPosts = await deliveryClient
        .items<BlogPost>()
        .type(contentTypes.blog_post.codename)
        .toPromise()
---
```

```astro
---
import { deliveryClient } from '../../lib/kontent';
import type { BlogPost } from '../../models';
import { contentTypes } from '../../models/project/contentTypes';


export async function getStaticPaths() {
    const blogPosts = await deliveryClient
        .items<BlogPost>()
        .type(contentTypes.blog_post.codename)
        .toPromise()


    return blogPosts.data.items.map(blogPost => ({
        params: { slug: blogPost.elements.url_slug.value },
        props: { blogPost }
    }))
}
---
```

--------------------------------

### Build Astro Site for Production with Bun

Source: https://v6.docs.astro.build/en/recipes/bun

Builds the Astro site for production deployment using Bun. This command generates optimized static assets for your website.

```bash
bun run build
```

--------------------------------

### Install Fontsource Package for Twinkle Star Font

Source: https://v6.docs.astro.build/en/guides/fonts

Demonstrates installing the Twinkle Star font package from Fontsource using different package managers (npm, pnpm, Yarn). Fontsource simplifies the process of using Google Fonts and other open-source fonts.

```bash
npm install @fontsource/twinkle-star
```

```bash
pnpm add @fontsource/twinkle-star
```

```bash
yarn add @fontsource/twinkle-star
```

--------------------------------

### Install Specific Astro and Integration Versions (Yarn)

Source: https://v6.docs.astro.build/en/upgrade-astro

Installs a specific version of Astro (4.5.3) and the Astro React integration (3.0.10) using Yarn. This method allows for pinning exact versions of dependencies.

```bash
yarn add astro@4.5.3 @astrojs/react@3.0.10
```

--------------------------------

### Install JSON:API Dependencies for Astro (Yarn)

Source: https://v6.docs.astro.build/en/guides/cms/drupal

Install the 'jsona' and 'drupal-jsonapi-params' Yarn packages to simplify working with JSON:API data in your Astro application. These packages assist with data transformation and query construction.

```bash
yarn add jsona drupal-jsonapi-params

```

--------------------------------

### Install Specific Astro and Integration Versions (npm)

Source: https://v6.docs.astro.build/en/upgrade-astro

Installs a specific version of Astro (4.5.3) and the Astro React integration (3.0.10) using npm. This is useful for maintaining compatibility with older projects or specific feature sets.

```bash
npm install astro@4.5.3 @astrojs/react@3.0.10
```

--------------------------------

### Install Tailwind Typography with npm

Source: https://v6.docs.astro.build/en/recipes/tailwind-rendered-markdown

Installs the `@tailwindcss/typography` package as a development dependency using npm. This package is essential for enabling Tailwind's typography styling capabilities.

```bash
npm install -D @tailwindcss/typography
```

--------------------------------

### Add Netlify Adapter using pnpm

Source: https://v6.docs.astro.build/en/guides/on-demand-rendering

Installs the Netlify adapter for Astro using the pnpm package manager. This command adds the adapter and updates your astro.config.mjs file.

```bash
pnpm astro add netlify
```

--------------------------------

### Enable Client-Side Navigation in Astro

Source: https://v6.docs.astro.build/en/guides/view-transitions

An example of a standard anchor tag in Astro that will be handled by the `ClientRouter` for client-side navigation, assuming `<ClientRouter />` is present in the layout. This allows for smooth transitions without full page reloads.

```html
<a href="/articles/emperor-penguins">

```

--------------------------------

### Install Tailwind 4 with Astro CLI

Source: https://v6.docs.astro.build/en/guides/styling

Installs the official Vite Tailwind plugin for Astro version 5.2.0 and later using the `astro add tailwind` command. This command automatically sets up Tailwind CSS for your project.

```bash
npx astro add tailwind

```

```bash
pnpm astro add tailwind

```

```bash
yarn astro add tailwind

```

--------------------------------

### Install Zephyr Integration Automatically (npm, pnpm, Yarn)

Source: https://v6.docs.astro.build/en/guides/deploy/zephyr

Automatically adds the Zephyr integration to your Astro project and updates the astro.config.mjs file. This command installs the integration and prepares your project for deployment.

```bash
npx with-zephyr@latest
```

```bash
pnpm dlx with-zephyr@latest
```

```bash
yarn dlx with-zephyr@latest
```

--------------------------------

### Upload Video to Mux using Mux Node SDK in Astro

Source: https://v6.docs.astro.build/en/guides/media/mux

This snippet demonstrates how to initiate a video upload to Mux using the Mux Node SDK within an Astro component. It requires Mux API access tokens to be configured as environment variables. The `create()` function is used to start the upload process, and the resulting upload URL is passed to the `MuxUploader` component.

```astro
---
import Layout from '../../layouts/Layout.astro';
import Mux from "@mux/mux-node";
import { MuxUploader } from "@mux/mux-uploader-astro";


const mux = new Mux({
  tokenId: import.meta.env.MUX_TOKEN_ID,
  tokenSecret: import.meta.env.MUX_TOKEN_SECRET
});


const upload = await mux.video.uploads.create({
  new_asset_settings: {
    playback_policy: ['public'],
    video_quality: 'basic'
  },
  cors_origin: '*',
});
---
<Layout title="Upload a video to Mux">
  <MuxUploader endpoint={upload.url} />
</Layout>

```

--------------------------------

### Call app.render() Method (JavaScript)

Source: https://v6.docs.astro.build/en/reference/adapter-reference

Demonstrates the basic usage of the `app.render()` method, which takes a `Request` object and returns a `Promise` resolving to a `Response` object.

```javascript
const response = await app.render(request);
```

--------------------------------

### Update Astro Dependency using pnpm

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

Updates the Astro dependency to the latest version using pnpm. It also shows how to update all project dependencies.

```bash
# updates the astro dependency:
pnpm upgrade astro
# or, to update all dependencies:
pnpm upgrade
```

--------------------------------

### Listen for TRANSITION_BEFORE_PREPARATION Event in Astro

Source: https://v6.docs.astro.build/en/reference/modules/astro-transitions

Provides a constant for the 'astro:before-preparation' event name to avoid using plain text strings. This example demonstrates adding an event listener for this specific transition phase.

```javascript
import { TRANSITION_BEFORE_PREPARATION } from "astro:transitions/client";


document.addEventListener(TRANSITION_BEFORE_PREPARATION, () => {
  /* the listener logic */
});
```

--------------------------------

### Initialize Supabase Client with PKCE Flow

Source: https://v6.docs.astro.build/en/guides/backend/supabase

Configures the Supabase client to use the 'pkce' (Proof Key for Code Exchange) authentication flow. This is essential for OAuth integrations and requires Supabase URL and Anon Key from environment variables.

```typescript
import { createClient } from "@supabase/supabase-js";


export const supabase = createClient(
  import.meta.env.SUPABASE_URL,
  import.meta.env.SUPABASE_ANON_KEY,
  {
    auth: {
      flowType: "pkce",
    },
  },
);

```

--------------------------------

### Astro About Page HTML Content

Source: https://v6.docs.astro.build/en/tutorial/2-pages/1

Example HTML content to populate an Astro 'About' page. This content is placed between the `<body>` tags of your `about.astro` file to define the page's structure and text.

```html
<body>
  <h1>My Astro Site</h1>
  <h1>About Me</h1>
  <h2>... and my new Astro site!</h2>


  <p>I am working through Astro's introductory tutorial. This is the second page on my website, and it's the first one I built myself!</p>


  <p>This site will update as I complete more of the tutorial, so keep checking back and see how my journey is going!</p>
</body>
```

--------------------------------

### Using an Astro Layout Component

Source: https://v6.docs.astro.build/en/basics/layouts

This example demonstrates how to use a previously defined Astro layout component ('MySiteLayout') to wrap page content. It passes a 'title' prop to the layout and injects paragraph content into the layout's slot.

```astro
---
import MySiteLayout from '../layouts/MySiteLayout.astro';
---
<MySiteLayout title="Home Page">
  <p>My page content, wrapped in a layout!</p>
</MySiteLayout>

```

--------------------------------

### Manage Global State with Inline Scripts

Source: https://v6.docs.astro.build/en/guides/view-transitions

When using inline scripts that might re-execute, it's important to manage global state carefully. This example shows how to check if a global object exists before creating it, preventing errors and ensuring the script behaves correctly even if executed multiple times.

```html
<script is:inline>
  if (!window.SomeGlobal) {
    window.SomeGlobal = {};
  }
</script>
```

--------------------------------

### Update Content Rendering with `render()` Function

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v6

Shows how to update content rendering by importing and using the `render()` function from `astro:content` instead of the deprecated `entry.render()` method.

```astro
---
import { getEntry, render } from 'astro:content';


const post = await getEntry('pages', 'homepage');


const { Content, headings } = await post.render();
const { Content, headings } = await render(post);
---
<Content />
```

--------------------------------

### nodeApp.setHeadersMap()

Source: https://v6.docs.astro.build/en/reference/adapter-reference

Loads headers configuration into the NodeApp instance.

```APIDOC
## nodeApp.setHeadersMap()

### Description
Loads headers configuration into the `NodeApp` instance.

### Method
`nodeApp.setHeadersMap(headers: NodeAppHeadersJson): void`

### Parameters
- **headers** (NodeAppHeadersJson) - Required - The headers configuration object.

### Example
```javascript
// Assuming 'nodeApp' is an instance of NodeApp
nodeApp.setHeadersMap([
  {
    pathname: "/blog",
    headers: [
      { key: "Content-Security-Policy", value: "default-src 'self'" },
    ]
  }
]);
```
```

--------------------------------

### Install Firebase Dependencies (npm, pnpm, Yarn)

Source: https://v6.docs.astro.build/en/guides/backend/firebase

Installs the 'firebase' and 'firebase-admin' packages required for client-side and server-side Firebase integration in an Astro project. Supports npm, pnpm, and Yarn package managers.

```bash
npm install firebase firebase-admin
```

```bash
pnpm add firebase firebase-admin
```

```bash
yarn add firebase firebase-admin
```

--------------------------------

### Configure Turso Environment Variables

Source: https://v6.docs.astro.build/en/guides/backend/turso

Set the TURSO_DATABASE_URL and TURSO_AUTH_TOKEN in your .env file. Ensure you do not use the PUBLIC_ prefix to keep these variables private.

```env
TURSO_DATABASE_URL=libsql://...
TURSO_AUTH_TOKEN=
```

--------------------------------

### Install Kontent.ai JS Model Generator, ts-node, and dotenv

Source: https://v6.docs.astro.build/en/guides/cms/kontent-ai

Installs the necessary Node.js packages for generating Kontent.ai content models and handling environment variables. These packages include the Kontent.ai model generator, ts-node for executing TypeScript files, and dotenv for managing environment variables.

```npm
npm install @kontent-ai/model-generator ts-node dotenv
```

```pnpm
pnpm add @kontent-ai/model-generator ts-node dotenv
```

```yarn
yarn add @kontent-ai/model-generator ts-node dotenv
```

--------------------------------

### Session Configuration with Redis

Source: https://v6.docs.astro.build/en/guides/integrations-guide/vercel

Configure Astro sessions to use Redis as a storage driver. This involves installing the `ioredis` package, setting up environment variables, and configuring the session driver in your Astro config.

```APIDOC
## POST /websites/v6_astro_build_en

### Description
Configure Astro sessions to use Redis as the storage driver.

### Method
POST

### Endpoint
/websites/v6_astro_build_en

### Parameters
#### Request Body
- **session.driver** (string) - Required - Set to `"redis"` to use Redis.
- **session.options.url** (string) - Required - The Redis connection URL, typically from an environment variable like `process.env.REDIS_URL`.

### Request Example
```json
{
  "session": {
    "driver": "redis",
    "options": {
      "url": "process.env.REDIS_URL"
    }
  }
}
```

### Response
#### Success Response (200)
- **message** (string) - Confirmation message.

#### Response Example
```json
{
  "message": "Session configuration updated to use Redis."
}
```
```

--------------------------------

### Install Mux Uploader Astro Component

Source: https://v6.docs.astro.build/en/guides/media/mux

Installs the Astro version of the Mux Uploader component using npm, pnpm, or Yarn. This component provides a customizable UI for video uploads directly within an Astro website.

```bash
npm install @mux/mux-uploader-astro
```

```bash
pnpm add @mux/mux-uploader-astro
```

```bash
yarn add @mux/mux-uploader-astro
```

--------------------------------

### Configure Local Font Variant with Display in Astro

Source: https://v6.docs.astro.build/en/reference/experimental-flags/fonts

Example of configuring a local font variant that includes the 'display' property, demonstrating that other remote font properties can be used within local variants.

```javascript
import { defineConfig } from "astro/config";


export default defineConfig({
    experimental: {
        fonts: [{
            provider: "local",
            name: "Custom",
            cssVariable: "--font-custom",
            variants: [
                {
                    weight: 400,
                    style: "normal",
                    src: ["./src/assets/fonts/custom-400.woff2"],
                    display: "block"
                }
            ]
        }]
    }
});
```

--------------------------------

### Display List of Blog Posts in Astro (HTML + JavaScript)

Source: https://v6.docs.astro.build/en/guides/cms/hashnode

This Astro component code snippet shows how to fetch and display a list of blog posts. It uses the `getAllPosts` function to retrieve post data and then maps over the `allPosts` array to render each post's title, brief content, cover image, and a link to the full post. This example assumes the `getAllPosts` function is available from a local module.

```astro
---
import { getAllPosts } from '../lib/client';


const data = await getAllPosts();
const allPosts = data.publication.posts.edges;


---


<html lang="en">
    <head>
        <title>Astro + Hashnode</title>
    </head>
    <body>


        {
            allPosts.map((post) => (
                <div>
                    <h2>{post.node.title}</h2>
                    <p>{post.node.brief}</p>
                    <img src={post.node.coverImage.url} alt={post.node.title} />
                    <a href={`/post/${post.node.slug}`}>Read more</a>
                </div>
            ))
        }
    </body>
</html>

```

--------------------------------

### Import npm Package Stylesheet (after config)

Source: https://v6.docs.astro.build/en/guides/styling

Demonstrates importing a stylesheet from an npm package after configuring Astro to handle it correctly (as shown in the previous example for packages not suggesting file extensions). This import will be bundled and optimized by Astro.

```astro
---
import 'package-name/normalize';
---
<html><!-- Your page here --></html>
```

--------------------------------

### Fetch GraphQL Data in Astro Component

Source: https://v6.docs.astro.build/en/guides/data-fetching

Illustrates how to query a GraphQL server using the global `fetch()` function within an Astro component. This example demonstrates making a POST request with a JSON body containing the GraphQL query and variables. The response data is then parsed and used to render page content.

```astro
---
const response = await fetch(
  "https://swapi-graphql.netlify.app/.netlify/functions/index",
  {
    method: "POST",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify({
      query: `
        query getFilm ($id:ID!) {
          film(id: $id) {
            title
            releaseDate
          }
        }
      `,
      variables: {
        id: "ZmlsbXM6MQ==",
      },
    }),
  }
);




const json = await response.json();
const { film } = json.data;
---
<h1>Fetching information about Star Wars: A New Hope</h1>
<h2>Title: {film.title}</h2>
<p>Year: {film.releaseDate}</p>

```

--------------------------------

### Add Bun Runtime Types to Astro Project

Source: https://v6.docs.astro.build/en/recipes/bun

Installs the `@types/bun` package as a development dependency. This provides runtime type definitions for Bun, improving type safety in your Astro project.

```bash
bun add -d @types/bun
```

--------------------------------

### Handle Live Entry Errors in Astro

Source: https://v6.docs.astro.build/en/guides/content-collections

Demonstrates how to gracefully handle errors when fetching a live entry using `getLiveEntry`. It checks for specific errors like `LiveEntryNotFoundError` and provides fallback mechanisms like logging errors or redirecting the user.

```javascript
import { LiveEntryNotFoundError } from 'astro/content/runtime';
import { getLiveEntry } from 'astro:content';


const { entry, error } = await getLiveEntry('products', Astro.params.id);


if (error) {
  if (error instanceof LiveEntryNotFoundError) {
    console.error(`Product not found: ${error.message}`);
    Astro.response.status = 404;
  } else {
    console.error(`Error loading product: ${error.message}`);
    return Astro.redirect('/500');
  }
}
```

--------------------------------

### Add Netlify Adapter using Yarn

Source: https://v6.docs.astro.build/en/guides/on-demand-rendering

Installs the Netlify adapter for Astro using the Yarn package manager. This command adds the adapter and updates your astro.config.mjs file.

```bash
yarn astro add netlify
```

--------------------------------

### Run Astro Development Server Programmatically

Source: https://v6.docs.astro.build/en/reference/programmatic-reference

The `dev()` function starts Astro's development server programmatically, similar to running `astro dev`. It accepts an `AstroInlineConfig` object for customization and returns a `DevServer` interface.

```javascript
import { dev } from "astro";


const devServer = await dev({
  root: "./my-project",
});


// Stop the server if needed
await devServer.stop();
```

--------------------------------

### Example Dev Toolbar App with Preact JSX

Source: https://v6.docs.astro.build/en/recipes/making-toolbar-apps

A sample Astro dev toolbar app demonstrating the use of JSX with Preact. It defines a component that displays a random motivational message when initialized.

```typescript
import { defineToolbarApp } from "astro/toolbar";
import { render } from "preact";


const motivationalMessages = [
  "You're doing great!",
  "Keep up the good work!",
  "You're awesome!",
  "You're a star!",
];


export default defineToolbarApp({
    init(canvas) {
      const message = motivationalMessages[Math.floor(Math.random() * motivationalMessages.length)];
      render(<h1>{message}</h1>, canvas);
    },
});

```

--------------------------------

### Manually Upgrade Astro Integrations (npm, pnpm, Yarn)

Source: https://v6.docs.astro.build/en/guides/integrations-guide

Instructions for manually upgrading specific Astro integrations like React and Partytown to their latest versions using npm, pnpm, or Yarn.

```bash
# Example: upgrade React and Partytown integrations
npm install @astrojs/react@latest @astrojs/partytown@latest
```

```bash
# Example: upgrade React and Partytown integrations
pnpm add @astrojs/react@latest @astrojs/partytown@latest
```

```bash
# Example: upgrade React and Partytown integrations
yarn add @astrojs/react@latest @astrojs/partytown@latest
```

--------------------------------

### Implement createExports for Server Entrypoints (JavaScript)

Source: https://v6.docs.astro.build/en/reference/adapter-reference

The `createExports` function is used in your server entrypoint to provide necessary exports for your host. It receives an SSR manifest and optional adapter arguments. This example shows how to export a `handler` function.

```javascript
import { App } from 'astro/app';


export function createExports(manifest) {
  const app = new App(manifest);


  const handler = (event, context) => {
    // ...
  };


  return { handler };
}
```

--------------------------------

### Set Up Environment Variable for Ghost API Key

Source: https://v6.docs.astro.build/en/guides/cms/ghost

Create a .env file in your Astro project's root directory to store your Ghost Content API key. This key is essential for authenticating API requests to your Ghost site.

```env
CONTENT_API_KEY=YOUR_API_KEY
```

--------------------------------

### Configure @astrojs/sitemap integration in astro.config.mjs

Source: https://v6.docs.astro.build/en/guides/integrations-guide/sitemap

Example of how to apply the sitemap integration to your Astro project by adding it to the `integrations` array in your configuration file.

```javascript
import { defineConfig } from 'astro/config';
import sitemap from '@astrojs/sitemap';


export default defineConfig({
  // ...
  integrations: [sitemap()],
});

```

--------------------------------

### includeFiles Option

Source: https://v6.docs.astro.build/en/guides/integrations-guide/netlify

Specify additional files to be bundled with your function, useful for files not automatically detected as dependencies.

```APIDOC
## POST /websites/v6_astro_build_en/includeFiles

### Description
Allows explicit specification of additional files to be bundled with your function. Useful for data files, configuration files, or template files not automatically detected as dependencies.

### Method
POST

### Endpoint
/websites/v6_astro_build_en/includeFiles

### Parameters
#### Request Body
- **includeFiles** (string[]) - Required - An array of file paths relative to your project's `root` to include.

### Request Example
```json
{
  "includeFiles": ["./my-data.json"]
}
```

### Response
#### Success Response (200)
- **message** (string) - Confirmation message.

#### Response Example
```json
{
  "message": "Files included successfully."
}
```
```

--------------------------------

### Add Vercel Adapter to Astro Project

Source: https://v6.docs.astro.build/en/guides/deploy/vercel

Installs the Vercel adapter for Astro to enable on-demand rendering. This command modifies the `astro.config.mjs` file.

```bash
npx astro add vercel
```

```bash
pnpm astro add vercel
```

```bash
yarn astro add vercel
```

--------------------------------

### Astro Page Structure with ClientRouter

Source: https://v6.docs.astro.build/en/guides/view-transitions

Illustrates the basic structure of an Astro page that utilizes the `<ClientRouter />` component for client-side routing. This setup is necessary for enabling Astro transitions and client-side navigation.

```html
---
import Form from "../components/Form.astro";
import { ClientRouter } from "astro:transitions";
---
<html>
  <head>
    <ClientRouter />
  </head>
  <body>
    <Form />
  </body>
</html>

```

--------------------------------

### Query Astro Build-Time Collections

Source: https://v6.docs.astro.build/en/guides/content-collections

Demonstrates how to query Astro content collections at build time using `getCollection` and `getEntry`. `getCollection` fetches all entries from a specified collection, while `getEntry` fetches a single entry by collection name and entry ID. Returned entries include `id`, `data`, and `body`.

```typescript
import { getCollection, getEntry } from 'astro:content';


// Get all entries from a collection.
// Requires the name of the collection as an argument.
const allBlogPosts = await getCollection('blog');


// Get a single entry from a collection.
// Requires the name of the collection and `id`
const poodleData = await getEntry('dogs', 'poodle');
```

--------------------------------

### Base Astro file structure

Source: https://v6.docs.astro.build/en/recipes/sharing-state-islands

An example of a base Astro file (`.astro`) demonstrating how to import and use client-side components like `CartFlyoutToggle`, `CartFlyout`, and `AddToCartForm`. The `client:load` directive indicates that these components should be hydrated on the client.

```html
---
import CartFlyoutToggle from '../components/CartFlyoutToggle';
import CartFlyout from '../components/CartFlyout';
import AddToCartForm from '../components/AddToCartForm';
---


<!DOCTYPE html>
<html lang="en">
<head>...</head>
<body>
  <header>
    <nav>
      <a href="/">Astro storefront</a>
      <CartFlyoutToggle client:load />
    </nav>
  </header>
  <main>
    <AddToCartForm client:load>
    <!-- ... -->
    </AddToCartForm>
  </main>
  <CartFlyout client:load />
</body>
</html>

```

--------------------------------

### Access Live Collections and Entries in Astro

Source: https://v6.docs.astro.build/en/guides/content-collections

Shows how to use `getLiveCollection()` and `getLiveEntry()` helper functions in Astro to fetch data from live collections. It includes examples of filtering collections by custom criteria and retrieving a specific entry by its ID.

```typescript
---
export const prerender = false; // Not needed in 'server' mode


import { getLiveCollection, getLiveEntry } from 'astro:content';


// Use loader-specific filters
const { entries: draftArticles } = await getLiveCollection('articles', {
  status: 'draft',
  author: 'john-doe',
});


// Get a specific product by ID
const { entry: product } = await getLiveEntry('products', Astro.params.slug);
---

```

--------------------------------

### Static File Endpoints - Binary Response

Source: https://v6.docs.astro.build/en/guides/endpoints

Example of creating a static endpoint that returns binary data, such as an image, by returning an ArrayBuffer from the Response.

```APIDOC
## GET /image.png

### Description
This endpoint fetches an image from a URL and returns its binary content, creating a static `/image.png` file.

### Method
GET

### Endpoint
`/image.png`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
None

### Response
#### Success Response (200)
- **(binary)** - The raw binary data of the image.

#### Response Example
(Binary image data)
```

--------------------------------

### Format Files with Prettier (npm)

Source: https://v6.docs.astro.build/en/editor-setup

Runs Prettier using npm to format all files in the current directory and its subdirectories. The `--write` flag modifies the files in place.

```bash
npx prettier . --write
```

--------------------------------

### Configure Amplify Build Settings for pnpm (Server-Rendered)

Source: https://v6.docs.astro.build/en/guides/deploy/aws

Specifies the build process for an Astro server-rendered site using pnpm with AWS Amplify adapter. Includes commands for dependency installation and cache management.

```yaml
version: 1
frontend:
  phases:
    preBuild:
      commands:
        - npm i -g pnpm
        - pnpm config set store-dir .pnpm-store
        - pnpm i
    build:
      commands:
        - pnpm run build
        - mv node_modules ./.amplify-hosting/compute/default
  artifacts:
    baseDirectory: .amplify-hosting
    files:
      - '**/*'
  cache:
    paths:
      - .pnpm-store/**/*
```

--------------------------------

### Alpine.js Entrypoint for Customization

Source: https://v6.docs.astro.build/en/guides/integrations-guide/alpinejs

A JavaScript file that configures Alpine.js instance before it starts. It accepts an Alpine instance and allows for plugins and custom directives.

```javascript
import type { Alpine } from 'alpinejs'
import intersect from '@alpinejs/intersect'


export default (Alpine: Alpine) => {
    Alpine.plugin(intersect)
}
```

--------------------------------

### Create Astro Project with Starlight Template using Yarn

Source: https://v6.docs.astro.build/en/guides/migrate-to-astro/from-pelican

This command initializes a new Astro project using the official Starlight documentation theme starter template via Yarn. It's another popular package manager option for setting up new Astro projects.

```bash
yarn create astro --template starlight
```

--------------------------------

### Configure Astro with Keystatic Integration

Source: https://v6.docs.astro.build/en/guides/cms/keystatic

Integrate Keystatic into your Astro project by adding it to the `integrations` array in your `astro.config.ts` file. This enables Keystatic functionality within your Astro build.

```typescript
import { defineConfig } from 'astro/config'


import react from '@astrojs/react'
import markdoc from '@astrojs/markdoc'
import keystatic from '@keystatic/astro'


// https://astro.build/config
export default defineConfig({
  integrations: [react(), markdoc(), keystatic()],
  output: 'static',
})
```

--------------------------------

### Dynamically generate robots.txt with sitemap URL in Astro

Source: https://v6.docs.astro.build/en/guides/integrations-guide/sitemap

Example of creating a `src/pages/robots.txt.ts` file to dynamically generate the `robots.txt` content, including the sitemap URL based on the configured site.

```typescript
import type { APIRoute } from 'astro';


const getRobotsTxt = (sitemapURL: URL) => `\
User-agent: *
Allow: /


Sitemap: ${sitemapURL.href}
`;


export const GET: APIRoute = ({ site }) => {
  const sitemapURL = new URL('sitemap-index.xml', site);
  return new Response(getRobotsTxt(sitemapURL));
};

```

--------------------------------

### Render Astro Component to Response using renderToResponse

Source: https://v6.docs.astro.build/en/reference/container-reference

This example illustrates how to use the `renderToResponse` function to render an Astro component (`Card`) within an Astro container, returning a `Response` object. It requires importing `experimental_AstroContainer` and the component.

```javascript
import { experimental_AstroContainer } from "astro/container";
import Card from "../src/components/Card.astro";


const container = await experimental_AstroContainer.create();
const result = await container.renderToResponse(Card);
```

--------------------------------

### Index Astro Page with Footer

Source: https://v6.docs.astro.build/en/tutorial/3-components/2

This is an example of an 'index.astro' file that includes navigation, a page title, and the custom 'Footer' component. It demonstrates the integration of multiple components and global CSS within an Astro page.

```astro
---
import Navigation from '../components/Navigation.astro';
import Footer from '../components/Footer.astro';
import '../styles/global.css';


const pageTitle = 'Home Page';
---


<html lang="en">
  <head>
    <meta charset="utf-8" />
    <link rel="icon" type="image/svg+xml" href="/favicon.svg" />
    <meta name="viewport" content="width=device-width" />
    <meta name="generator" content={Astro.generator} />
    <title>{pageTitle}</title>
  </head>
  <body>
    <Navigation />
    <h1>{pageTitle}</h1>
    <Footer />
  </body>
</html>

```

--------------------------------

### Configure Amplify Build Settings for Yarn (Server-Rendered)

Source: https://v6.docs.astro.build/en/guides/deploy/aws

Specifies the build process for an Astro server-rendered site using Yarn with AWS Amplify adapter. Includes commands for dependency installation and moving node_modules.

```yaml
version: 1
frontend:
  phases:
    preBuild:
      commands:
        - yarn install
    build:
      commands:
        - yarn build
        - mv node_modules ./.amplify-hosting/compute/default
  artifacts:
    baseDirectory: .amplify-hosting
    files:
      - '**/*'
  cache:
    paths:
      - node_modules/**/*
```

--------------------------------

### Handle Mux Uploader Events in Astro

Source: https://v6.docs.astro.build/en/guides/media/mux

This example shows how to handle various events emitted by the `<MuxUploader />` component within an Astro application using client-side JavaScript. It demonstrates listening for events such as 'uploadstart', 'success', 'uploaderror', and 'progress' to provide feedback or trigger actions based on the upload's lifecycle. The `MuxUploaderElement` type is available for TypeScript users.

```astro
---
import { MuxUploader } from '@mux/mux-uploader-astro';
---


<MuxUploader
  id="my-uploader"
  endpoint="https://my-authenticated-url/storage?your-url-params"
  pausable
/>


<script>
  import type { MuxUploaderElement } from '@mux/mux-uploader-astro';


  const uploader = document.getElementById('my-uploader') as MuxUploaderElement;


  uploader.addEventListener('uploadstart', (event) => {
    console.log('Upload started!', event.detail);
  });


  uploader.addEventListener('success', (event) => {
    console.log('Upload successful!', event.detail);
  });


  uploader.addEventListener('uploaderror', (event) => {
    console.error('Upload error!', event.detail);
  });


  uploader.addEventListener('progress', (event) => {
    console.log('Upload progress: ', event.detail);
  });
</script>

```

--------------------------------

### CSS Order of Appearance Example in Astro

Source: https://v6.docs.astro.build/en/guides/styling

Illustrates how the order of appearance determines style precedence when CSS rules have the same specificity. The last rule defined takes precedence.

```html
<style>
  h1 { color: purple }
  h1 { color: red }
</style>
<div>
  <h1>
    This header will be red!
  </h1>
</div>
```

--------------------------------

### Update Astro Dependency using npm

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

Updates the Astro dependency to the latest version using npm. It also shows how to update all project dependencies.

```bash
# updates the astro dependency:
npm upgrade astro
# or, to update all dependencies:
npm upgrade
```

--------------------------------

### Build Astro Site (pnpm)

Source: https://v6.docs.astro.build/en/guides/deploy/deno

Builds the Astro project for production using pnpm. This command generates the static or server-rendered output in the `dist` directory.

```bash
pnpm run build
```

--------------------------------

### Prefetching with Multiple Links (FIFO Strategy)

Source: https://v6.docs.astro.build/en/guides/prefetch

Illustrates how to use the `eagerness: 'moderate'` option with multiple links to leverage First In, First Out (FIFO) strategies and browser heuristics for prefetching.

```APIDOC
## Prefetching with Multiple Links (FIFO Strategy)

### Description
When dealing with a large number of links, setting `eagerness: 'moderate'` in the `prefetch()` function allows the browser to manage prefetching using FIFO strategies and its own heuristics, optimizing resource usage.

### Method
`prefetch(href: string, options?: { eagerness: 'moderate' }): void`

### Endpoint
`astro:prefetch` (module import)

### Parameters
#### Query Parameters
None

#### Request Body
None

### Request Example
```html
<a class="link-moderate" href="/nice-link-1">A Nice Link 1</a>
<a class="link-moderate" href="/nice-link-2">A Nice Link 2</a>
...
<a class="link-moderate" href="/nice-link-20">A Nice Link 20</a>

<script>
  import { prefetch } from 'astro:prefetch';

  const linkModerate = document.getElementsByClassName('link-moderate');
  linkModerate.forEach((link) => {
    prefetch(link.getAttribute('href'), { eagerness: 'moderate' });
  });
</script>
```

### Response
#### Success Response (200)
N/A (This is a client-side function)

#### Response Example
N/A
```

--------------------------------

### Filesystem Watching with watcher in JavaScript

Source: https://v6.docs.astro.build/en/reference/content-loader-reference

In development mode, the `watcher` object provides a filesystem watcher to trigger updates. This example demonstrates how to use it to reload data from a file when it changes.

```javascript
return {
  name: 'file-loader',
  load: async ({ config, store, watcher }) => {
    const url = new URL(fileName, config.root);
    const filePath = fileURLToPath(url);
    await syncData(filePath, store);


    watcher?.on('change', async (changedPath) => {
      if (changedPath === filePath) {
        logger.info(`Reloading data from ${fileName}`);
        await syncData(filePath, store);
      }
    });
  },
};

```

--------------------------------

### Configure Amplify Build Settings for pnpm (Static)

Source: https://v6.docs.astro.build/en/guides/deploy/aws

Specifies the build process for an Astro static site using pnpm with AWS Amplify. It includes commands for installing pnpm, dependencies, building the site, and managing cache.

```yaml
version: 1
frontend:
  phases:
    preBuild:
      commands:
        - npm i -g pnpm
        - pnpm config set store-dir .pnpm-store
        - pnpm i
    build:
      commands:
        - pnpm run build
  artifacts:
    baseDirectory: /dist
    files:
      - '**/*'
  cache:
    paths:
      - .pnpm-store/**/*
```

--------------------------------

### Run Build Command (npm, pnpm, Yarn)

Source: https://v6.docs.astro.build/en/recipes/analyze-bundle-size

Executes the build command for your Astro project using npm, pnpm, or Yarn. This command triggers the bundling process, including the visualization generated by `rollup-plugin-visualizer`.

```bash
npm run build
```

```bash
pnpm build
```

```bash
yarn build
```

--------------------------------

### Deploy Static Astro Site via CLI

Source: https://v6.docs.astro.build/en/guides/deploy/deno

Deploys a static Astro site to Deno Deploy after navigating to the 'dist' directory. It uses the 'deployctl' command with a file server entry point.

```bash
cd dist && deployctl deploy jsr:@std/http/file-server
```

--------------------------------

### Initialize Supabase Client in Astro

Source: https://v6.docs.astro.build/en/guides/backend/supabase

Create a Supabase client instance in your Astro project by importing `createClient` from `@supabase/supabase-js` and initializing it with your Supabase URL and anonymous key from environment variables. This client will be used for all Supabase interactions.

```typescript
import { createClient } from "@supabase/supabase-js";


export const supabase = createClient(
  import.meta.env.SUPABASE_URL,
  import.meta.env.SUPABASE_ANON_KEY,
);
```

--------------------------------

### Initialize ButterCMS Client in Astro

Source: https://v6.docs.astro.build/en/guides/cms/buttercms

Initializes the ButterCMS client using the API token from environment variables and exports it for use in an Astro project.

```javascript
import Butter from "buttercms";


export const butterClient = Butter(import.meta.env.BUTTER_TOKEN);
```

--------------------------------

### Building a Custom Session Driver

Source: https://v6.docs.astro.build/en/reference/session-driver-reference

This section details how to build a custom session driver for Astro, consisting of a driver config and implementation. It covers the `SessionDriverConfig` interface and provides an example of a memory driver.

```APIDOC
## Building a Session Driver

### Description
A session driver is made of two parts: the driver config and the driver implementation.

### The Session Driver Config

#### Description
The `SessionDriverConfig` is an object containing a required `entrypoint` and an optional `config`. It's typically implemented by exporting a function that returns this object.

#### Method
N/A (Configuration)

#### Endpoint
N/A (Configuration)

#### Parameters
##### Path Parameters
N/A

##### Query Parameters
N/A

##### Request Body
N/A

#### Request Example (Memory Driver Config)
```javascript
import type { SessionDriverConfig } from 'astro'


export interface Config {
    max?: number;
}


export function memoryDriver(config: Config = {}): SessionDriverConfig {
    return {
        entrypoint: new URL('./runtime.js', import.meta.url),
        config,
    }
}
```

#### Registering the Driver
```javascript
import { defineConfig } from 'astro/config'
import { memoryDriver } from './driver/config'


export default defineConfig({
    session: {
        driver: memoryDriver({
            max: 500
        })
    }
})
```

#### `entrypoint`
**Type:** `string | URL`
**Description:** Defines the entrypoint for the driver implementation.

#### `config`
**Type:** `Record<string, any> | undefined`
**Description:** Defines the serializable config passed to the driver implementation at runtime.

### The Session Driver Implementation

#### Description
A `SessionDriver` is an object responsible for storing, retrieving, and deleting session data at runtime. It's implemented by exporting a default function that accepts the driver config.

#### Method
N/A (Implementation)

#### Endpoint
N/A (Implementation)

#### Parameters
##### Path Parameters
N/A

##### Query Parameters
N/A

##### Request Body
N/A

#### Request Example (Memory Driver Implementation)
```javascript
import type { SessionDriver } from 'astro'
import type { Config } from './config'
import { LRUCache } from 'lru-cache'


export default function(config: Config): SessionDriver {
    const cache = new LRUCache({ max: config.max })
    return {
        setItem: async (key, value) => {
            cache.set(key, value)
        },
        getItem: async (key) => {
            return cache.get(key)
        },
        removeItem: async (key) => {
            cache.delete(key)
        },
    }
}
```

#### `setItem()`
**Type:** `(key: string, value: any) => Promise<void>`
**Description:** Sets session data by key.

#### `getItem()`
**Type:** `(key: string) => Promise<any>`
**Description:** Retrieves session data by key.

#### `removeItem()`
**Type:** `(key: string) => Promise<void>`
**Description:** Removes session data by key.
```

--------------------------------

### Deploy On-Demand Astro Site via CLI

Source: https://v6.docs.astro.build/en/guides/deploy/deno

Deploys an on-demand Astro site to Deno Deploy using the 'deployctl' command, specifying the entry point for the server.

```bash
deployctl deploy ./dist/server/entry.mjs
```

--------------------------------

### Configure Redis Session Driver in Astro

Source: https://v6.docs.astro.build/en/guides/integrations-guide/vercel

Configure the Astro session driver to use 'redis' and provide the Redis connection URL via `process.env.REDIS_URL`. This setup is part of the `@astrojs/vercel` adapter configuration.

```javascript
import { defineConfig } from 'astro/config';
import vercel from '@astrojs/vercel';


export default defineConfig({
  adapter: vercel(),
  session: {
    driver: 'redis',
    options: {
      url: process.env.REDIS_URL,
    },
  },
});
```

--------------------------------

### Set site URL in astro.config.mjs for @astrojs/sitemap

Source: https://v6.docs.astro.build/en/guides/integrations-guide/sitemap

Configuration example showing how to set the `site` option in `astro.config.mjs`, which is required by the sitemap integration to generate correct URLs.

```javascript
import { defineConfig } from 'astro/config';
import sitemap from '@astrojs/sitemap';


export default defineConfig({
  site: 'https://example.com',
  integrations: [sitemap()],
  // ...
});

```

--------------------------------

### Astro Markdown Frontmatter Example

Source: https://v6.docs.astro.build/en/guides/markdown-content

Demonstrates how to define frontmatter properties (like title and author) in a Markdown file and include body content. This frontmatter is accessible within Astro components.

```markdown
---
title: 'The greatest post of all time'
author: 'Ben'
---


Here is my _great_ post!

```

--------------------------------

### markdown.syntaxHighlight Configuration

Source: https://v6.docs.astro.build/en/reference/configuration-reference

Choose and configure the syntax highlighter for Markdown code blocks. Options include Shiki, Prism, or disabling highlighting entirely.

```APIDOC
## markdown.syntaxHighlight

### Description

Determines which syntax highlighter to use for Markdown code blocks (```). This affects the CSS classes applied to your code blocks. Can be set to 'shiki', 'prism', or `false`.

### Type

`SyntaxHighlightConfig | SyntaxHighlightConfigType | false`

### Default

`{ type: 'shiki', excludeLangs: ['math'] }`

### Options

- **`'shiki'`**: Use the Shiki highlighter (default).
- **`'prism'`**: Use the Prism highlighter and provide your own stylesheet.
- **`false`**: Disable syntax highlighting.

### Configuration Object

For more granular control, use a configuration object:

#### markdown.syntaxHighlight.type

- **Type:** `'shiki' | 'prism'`
- **Default:** `'shiki'`
- **Added in:** `astro@5.5.0`
- Specifies the highlighter engine.

#### markdown.syntaxHighlight.excludeLangs

- **Type:** `Array<string>`
- **Default:** `['math']`
- **Added in:** `astro@5.5.0`
- An array of languages to exclude from default syntax highlighting. Useful for diagramming tools like Mermaid.

### Example Usage

```javascript
// Using a string value
{
  markdown: {
    syntaxHighlight: 'prism',
  }
}

// Using a configuration object
import { defineConfig } from 'astro/config';

export default defineConfig({
  markdown: {
    syntaxHighlight: {
      type: 'shiki',
      excludeLangs: ['mermaid', 'math'],
    },
  },
});
```
```

--------------------------------

### Handle Dynamic Route with GET Request and Response - Astro API

Source: https://v6.docs.astro.build/en/guides/endpoints

This snippet demonstrates how to create a dynamic API route in Astro that handles GET requests. It fetches product data based on the route parameter 'id' and returns a JSON response or a 404 error. It utilizes the `Response` object to set status codes and headers.

```javascript
import { getProduct } from "../db";


export async function GET({ params }) {
  const id = params.id;
  const product = await getProduct(id);


  if (!product) {
    return new Response(null, {
      status: 404,
      statusText: "Not found",
    });
  }


  return new Response(JSON.stringify(product), {
    status: 200,
    headers: {
      "Content-Type": "application/json",
    },
  });
}
```

--------------------------------

### Update Astro Dependency using Yarn

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

Updates the Astro dependency to the latest version using Yarn. It also shows how to update all project dependencies.

```bash
# updates the astro dependency:
yarn upgrade astro
# or, to update all dependencies:
yarn upgrade
```

--------------------------------

### Place Imports at Top of Frontmatter

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

A bug in Astro v0.21+ requires all imports within components to be placed at the very top of the frontmatter section.

```astro
---
import Component from '../components/Component.astro'
const whereShouldIPutMyImports = "on top!"
---
```

--------------------------------

### Set Environment Variables via CLI (pnpm)

Source: https://v6.docs.astro.build/en/guides/environment-variables

Example of setting a public environment variable (`PUBLIC_POKEAPI`) when running an Astro development server using pnpm.

```bash
PUBLIC_POKEAPI=https://pokeapi.co/api/v2 pnpm run dev
```

--------------------------------

### Login to Zerops CLI

Source: https://v6.docs.astro.build/en/guides/deploy/zerops

Logs the Zerops CLI into your account using a generated access token. Ensure you have obtained an access token from the Zerops app settings.

```bash
zcli login <token>
```

--------------------------------

### Add Supabase Credentials to .env File

Source: https://v6.docs.astro.build/en/guides/backend/supabase

Configure your Astro project to use Supabase by adding your Supabase URL and anonymous key to the `.env` file. These environment variables are essential for initializing the Supabase client and accessing your project's resources.

```env
SUPABASE_URL=YOUR_SUPABASE_URL
SUPABASE_ANON_KEY=YOUR_SUPABASE_ANON_KEY
```

--------------------------------

### Implement Login/Logout Buttons in Astro

Source: https://v6.docs.astro.build/en/guides/authentication

This Astro component example shows how to add interactive login and logout buttons to your page. It dynamically imports the `signIn` and `signOut` functions and attaches click handlers to the buttons to initiate authentication flows.

```astro
---
import Layout from 'src/layouts/Base.astro';
---
<Layout>
  <button id="login">Login</button>
  <button id="logout">Logout</button>


  <script>
    const { signIn, signOut } = await import("./lib/auth-client")
    document.querySelector("#login").onclick = () => signIn.social({
      provider: "github",
      callbackURL: "/dashboard",
    })
    document.querySelector("#logout").onclick = () => signOut()
  </script>
</Layout>

```

--------------------------------

### Define Named Exports for Server Entrypoint

Source: https://v6.docs.astro.build/en/reference/adapter-reference

Specifies an array of named exports to be used with the `createExports()` function of the server entrypoint. This example assumes `createExports()` provides an export named `handler`.

```javascript
export default function createIntegration() {
  return {
    name: '@example/my-adapter',
    hooks: {
      'astro:config:done': ({ config, setAdapter }) => {
        setAdapter({
          name: '@example/my-adapter',
          serverEntrypoint: '@example/my-adapter/server.js',
          exports: ['handler']
        });
      },
    },
  };
}
```

--------------------------------

### Parse CSV File with Custom Parser using file() Loader (JavaScript)

Source: https://v6.docs.astro.build/en/guides/content-collections

Demonstrates how to use the `file()` loader with a custom `parser` function to load data from unsupported file types, such as CSV. This example uses the 'csv-parse/sync' library to parse the CSV content.

```javascript
import { defineCollection } from "astro:content";
import { file } from "astro/loaders";
import { parse as parseCsv } from "csv-parse/sync";


const cats = defineCollection({
  loader: file("src/data/cats.csv", {
    parser: (text) => parseCsv(text, { columns: true, skipEmptyLines: true }),
  }),
});

```

--------------------------------

### Include FeedbackForm Component (Astro)

Source: https://v6.docs.astro.build/en/recipes/build-forms-api

These examples show how to import and use the `FeedbackForm` component within an Astro project. The `client:load` directive is used to ensure that the component's client-side JavaScript is hydrated when the page loads, enabling its interactive functionality.

```astro
---
import FeedbackForm from "../components/FeedbackForm"
---
<FeedbackForm client:load />
```

```astro
---
import FeedbackForm from "../components/FeedbackForm"
---
<FeedbackForm client:load />
```

```astro
---
import FeedbackForm from "../components/FeedbackForm"
---
<FeedbackForm client:load />
```

```astro
---
import FeedbackForm from "../components/FeedbackForm.svelte"
---
<FeedbackForm client:load />
```

```astro
---
import FeedbackForm from "../components/FeedbackForm.vue"
---
<FeedbackForm client:load />
```

--------------------------------

### Configure GitLab CI/CD for Astro Deployment

Source: https://v6.docs.astro.build/en/guides/deploy/gitlab

Sets up the `.gitlab-ci.yml` file to automate the build and deployment of an Astro site to GitLab Pages. It uses a Node.js image, installs dependencies, runs the build command, and specifies the 'public' directory as the artifact to be published. The pipeline is triggered on pushes to the 'main' branch.

```yaml
pages:
  # The Docker image that will be used to build your app
  image: node:lts


  before_script:
    - npm ci


  script:
    # Specify the steps involved to build your app here
    - npm run build


  artifacts:
    paths:
      # The folder that contains the built files to be published.
      # This must be called "public".
      - public


  only:
    # Trigger a new build and deploy only when there is a push to the
    # branch(es) below
    - main

```

--------------------------------

### Hydrate interactive framework components in Astro

Source: https://v6.docs.astro.build/en/guides/framework-components

Shows how to make framework components interactive using `client:*` directives. Different directives like `client:load`, `client:visible`, and `client:only` control when the component's JavaScript is sent to the browser and when it hydrates. This example includes components written in JSX and Svelte.

```astro
---
// Example: hydrating framework components in the browser.
import InteractiveButton from '../components/InteractiveButton.jsx';
import InteractiveCounter from '../components/InteractiveCounter.jsx';
import InteractiveModal from '../components/InteractiveModal.svelte';
---
<!-- This component's JS will begin importing when the page loads -->
<InteractiveButton client:load />


<!-- This component's JS will not be sent to the client until
the user scrolls down and the component is visible on the page -->
<InteractiveCounter client:visible />


<!-- This component won't render on the server, but will render on the client when the page loads -->
<InteractiveModal client:only="svelte" />

```

--------------------------------

### Build Astro Site for Production using npm, pnpm, or Yarn

Source: https://v6.docs.astro.build/en/develop-and-build

These commands build a production-ready version of your Astro site, typically outputting to a 'dist/' folder. This process also checks for build errors and type errors if TypeScript is configured strictly. After building, you can preview the built site locally.

```bash
npm run build
```

```bash
pnpm build
```

```bash
yarn run build
```

--------------------------------

### Configure glob() Loader to Retain Uppercase IDs (JavaScript)

Source: https://v6.docs.astro.build/en/guides/content-collections

Illustrates how to configure the `glob()` loader within `defineCollection` to customize ID generation. This example specifically shows how to retain uppercase letters in the ID by overriding the default `generateId` behavior.

```javascript
import { defineCollection } from 'astro:content';
import { glob } from 'astro:content';


const authors = defineCollection({
  /* Retrieve all JSON files in your authors directory while retaining
   * uppercase letters in the ID. */
  loader: glob({
    pattern: '**/*.json',
    base: "./src/data/authors",
    generateId: ({ entry }) => entry.replace(/\.json$/, ''),
  }),
});

```

--------------------------------

### Astro Markdown Import Properties Example

Source: https://v6.docs.astro.build/en/guides/markdown-content

Demonstrates the structure of the `Astro.props` object when importing Markdown files in Astro. It includes properties like `file`, `url`, `frontmatter`, `getHeadings()`, `rawContent()`, and `compiledContent()`.

```javascript
Astro.props = {
  file: "/home/user/projects/.../file.md",
  url: "/en/guides/markdown-content/",
  frontmatter: {
    /** Frontmatter from a blog post */
    title: "Astro 0.18 Release",
    date: "Tuesday, July 27 2021",
    author: "Matthew Phillips",
    description: "Astro 0.18 is our biggest release since Astro launch.",
  },
  getHeadings: () => [
    {"depth": 1, "text": "Astro 0.18 Release", "slug": "astro-018-release"},
    {"depth": 2, "text": "Responsive partial hydration", "slug": "responsive-partial-hydration"}
    /* ... */
  ],
  rawContent: () => "# Astro 0.18 Release\n<p>A little over a month ago, the first public beta [...]",
  compiledContent: () => "<h1>Astro 0.18 Release</h1>\n<p>A little over a month ago, the first public beta [...]</p>",
}
```

--------------------------------

### Set Environment Variables via CLI (npm)

Source: https://v6.docs.astro.build/en/guides/environment-variables

Example of setting a public environment variable (`PUBLIC_POKEAPI`) when running an Astro development server using npm.

```bash
PUBLIC_POKEAPI=https://pokeapi.co/api/v2 npm run dev
```

--------------------------------

### Using next() with a Rewrite Path

Source: https://v6.docs.astro.build/en/guides/middleware

Shows how to use the `next()` function with a path parameter to rewrite the current `Request` without retriggering a new rendering phase. This is useful for passing modified requests to subsequent middleware.

```APIDOC
## GET /items/{id}

### Description
Retrieves details for a specific item by its ID.

### Method
GET

### Endpoint
/items/{id}

### Parameters
#### Path Parameters
- **id** (string) - Required - The unique identifier of the item to retrieve.

#### Query Parameters
- **include_details** (boolean) - Optional - If true, includes additional details about the item.

### Response
#### Success Response (200)
- **id** (string) - The unique identifier of the item.
- **name** (string) - The name of the item.
- **description** (string) - A brief description of the item.
- **details** (object) - Optional - Additional details about the item, present only if `include_details` is true.

#### Response Example
```json
{
  "id": "item_456def",
  "name": "Example Widget",
  "description": "A sample widget for demonstration purposes.",
  "details": {
    "color": "blue",
    "weight": "1kg"
  }
}
```
```

--------------------------------

### Infer getStaticPaths() Types with InferGetStaticParamsType and InferGetStaticPropsType

Source: https://v6.docs.astro.build/en/guides/typescript

Astro includes helpers to infer types from your `getStaticPaths()` function. `InferGetStaticParamsType` gets the type of `Astro.params`, `InferGetStaticPropsType` gets the type of `Astro.props`, and `GetStaticPaths` can infer both simultaneously.

```typescript
import type {
  InferGetStaticParamsType,
  InferGetStaticPropsType,
  GetStaticPaths,
} from "astro";


export const getStaticPaths = (async () => {
  const posts = await getCollection("blog");
  return posts.map((post) => {
    return {
      params: { id: post.id },
      props: { draft: post.data.draft, title: post.data.title },
    };
  });
}) satisfies GetStaticPaths;


type Params = InferGetStaticParamsType<typeof getStaticPaths>;
type Props = InferGetStaticPropsType<typeof getStaticPaths>;


const { id } = Astro.params as Params;
//                   ^? { id: string; }


const { title } = Astro.props;
//                      ^? { draft: boolean; title: string; }

```

--------------------------------

### Configure Astro Project for Juno Deployment

Source: https://v6.docs.astro.build/en/guides/deploy/juno

This configuration file sets up your Astro project for deployment to Juno. It specifies the production satellite ID, the source directory for static assets, and the build command to run before deployment. Ensure you replace `<PROD_SATELLITE_ID>` with your actual satellite ID.

```javascript
import { defineConfig } from '@junobuild/config';


/** @type {import('@junobuild/config').JunoConfig} */
export default defineConfig({
  satellite: {
    ids: {
      production: '<PROD_SATELLITE_ID>'
    },
    source: 'dist',
    predeploy: ['npm run build']
  }
});
```

--------------------------------

### Generate Binary Image Endpoint in Astro

Source: https://v6.docs.astro.build/en/guides/endpoints

This example shows how to create an endpoint that generates a binary image file, such as a PNG. It fetches an image from a URL and returns its ArrayBuffer in the Response. This is useful for dynamically generating images at build time.

```typescript
export async function GET({ params, request }) {
  const response = await fetch(
    "https://docs.astro.build/assets/full-logo-light.png",
  );


  return new Response(await response.arrayBuffer());
}
```

--------------------------------

### Set Per-Page Cache Control Headers

Source: https://v6.docs.astro.build/en/guides/integrations-guide/netlify

Manually control caching for individual pages by setting caching headers in the Astro response. This example demonstrates setting the `CDN-Cache-Control` header for fine-grained cache management.

```astro
---
import Layout from '../components/Layout.astro';


Astro.response.headers.set('CDN-Cache-Control', 'public, max-age=45, must-revalidate');
---


<Layout title="Astro on Netlify">
  {new Date()}
</Layout>
```

--------------------------------

### Wrangler Configuration for Custom Session KV Binding

Source: https://v6.docs.astro.build/en/guides/integrations-guide/cloudflare

Example Wrangler configuration file snippet to define a custom KV namespace binding for session storage. This should be used in conjunction with the `sessionKVBindingName` option in the Astro adapter configuration.

```json
{
  "kv_namespaces": [
    {
      "binding": "MY_SESSION_BINDING",
    }
  ]
}
```

--------------------------------

### Render Home Page with Storyblok in Astro

Source: https://v6.docs.astro.build/en/guides/cms/storyblok

Fetches content for the 'home' page from the Storyblok API and renders it using the StoryblokComponent. Requires the 'Page' component to be added to astro.config.mjs.

```astro
---
import { useStoryblokApi } from '@storyblok/astro'
import StoryblokComponent from '@storyblok/astro/StoryblokComponent.astro'
import BaseLayout from '../layouts/BaseLayout.astro'


const storyblokApi = useStoryblokApi();
const { data } = await storyblokApi.get('cdn/stories/home', {
  version: import.meta.env.DEV ? "draft" : "published",
});
const content = data.story.content;
---
<html lang="en">
  <head>
    <title>Storyblok & Astro</title>
  </head>
  <body>
    <StoryblokComponent blok={content} />
  </body>
</html>

```

--------------------------------

### Basic Astro Page Structure

Source: https://v6.docs.astro.build/en/recipes/build-forms

This snippet shows the basic structure of an Astro page, including the `<h1>` tag for a title. It serves as a starting point for adding form elements.

```astro
---
---
<h1>Register</h1>
```

--------------------------------

### Display list of blog posts in Astro component

Source: https://v6.docs.astro.build/en/guides/cms/cosmic

Fetches blog post data using the `getAllPosts` function and renders a list of posts within an Astro component. Each post's title, slug, excerpt, and tags are passed as props to a `Card` component for display.

```astro
---
import Card from '../components/Card.astro'
import { getAllPosts } from '../lib/cosmic'


const data = await getAllPosts()
---


<section>
  <ul class="grid gap-8 md:grid-cols-2">
    {
      data.map((post) => (
        <Card
          title={post.title}
          href={post.slug}
          body={post.metadata.excerpt}
          tags={post.metadata.tags.map((tag) => tag)}
        />
      ))
    }
  </ul>
</section>
```

--------------------------------

### Set Environment Variables via CLI (Yarn)

Source: https://v6.docs.astro.build/en/guides/environment-variables

Example of setting a public environment variable (`PUBLIC_POKEAPI`) when running an Astro development server using Yarn.

```bash
PUBLIC_POKEAPI=https://pokeapi.co/api/v2 yarn run dev
```

--------------------------------

### Create Astro Adapter with Dynamic Fetch Headers

Source: https://v6.docs.astro.build/en/reference/adapter-reference

This code snippet illustrates configuring the `client` option for an Astro adapter, specifically `internalFetchHeaders`. It demonstrates how to dynamically set fetch headers by retrieving a `DEPLOY_ID` from environment variables and returning it as a custom header if present.

```javascript
export default function createIntegration() {
  return {
    name: '@example/my-adapter',
    hooks: {
      'astro:config:done': ({ config, setAdapter }) => {
        setAdapter({
          name: '@example/my-adapter',
          serverEntrypoint: '@example/my-adapter/server.js',
          client: {
            internalFetchHeaders: () => {
              const deployId = process.env.DEPLOY_ID;
              return deployId ? { 'Your-Header-ID': deployId } : {};
            },
          },
        });
      },
    },
  };
}
```

--------------------------------

### Generator Version API

Source: https://v6.docs.astro.build/en/reference/api-reference

Get the current version of Astro your project is running. This is useful for meta tags or informational purposes.

```APIDOC
## GET /api/generator

### Description
Retrieves the current version of Astro being used by the project.

### Method
GET

### Endpoint
/api/generator

### Parameters
#### Query Parameters
None

#### Request Body
None

### Request Example
None

### Response
#### Success Response (200)
- **generator** (string) - The Astro version string (e.g., "Astro v5.x.x").

#### Response Example
```json
{
  "generator": "Astro v5.0.0"
}
```
```

--------------------------------

### Create Custom Astro Link Component

Source: https://v6.docs.astro.build/en/guides/migrate-to-astro/from-gatsby

Astro allows for custom components. This example shows how to create a reusable <Link> component in Astro that accepts a 'to' prop for navigation.

```astro
---
const { to } = Astro.props
---
<a href={to}><slot /></a>
```

--------------------------------

### Request Object API

Source: https://v6.docs.astro.build/en/reference/api-reference

Access the standard Request object to get details like URL, headers, method, and body of the incoming request.

```APIDOC
## GET /api/request

### Description
Provides access to the standard `Request` object, allowing retrieval of request details like URL, method, and headers.

### Method
GET

### Endpoint
/api/request

### Parameters
#### Query Parameters
None

#### Request Body
None

### Request Example
None

### Response
#### Success Response (200)
- **request** (Request) - The standard Request object containing details about the incoming request.

#### Response Example
```json
{
  "request": {
    "url": "https://example.com/api/request?query=test",
    "method": "GET",
    "headers": {
      "Content-Type": "application/json"
    }
  }
}
```
```

--------------------------------

### Specify Font Subsets (JavaScript)

Source: https://v6.docs.astro.build/en/reference/experimental-flags/fonts

Example of defining font subsets to preload. This is useful for ensuring specific character sets are available, improving rendering performance for different languages.

```javascript
subsets: ["latin"]
```

--------------------------------

### Get Astro Cookie Headers

Source: https://v6.docs.astro.build/en/reference/api-reference

Retrieves the header values for `Set-Cookie` that will be sent with the response. This is useful for inspecting the cookies being set.

```typescript
Astro.cookies.headers() => Iterator<string>;
```

--------------------------------

### Listen for TRANSITION_AFTER_SWAP Event in Astro

Source: https://v6.docs.astro.build/en/reference/modules/astro-transitions

Provides a constant for the 'astro:after-swap' event name, ensuring consistency and preventing typos. The example demonstrates attaching a listener to this event.

```javascript
import { TRANSITION_AFTER_SWAP } from "astro:transitions/client";


document.addEventListener(TRANSITION_AFTER_SWAP, () => {
  /* the listener logic */
});
```

--------------------------------

### Remove Astro Integration (npm, pnpm, Yarn)

Source: https://v6.docs.astro.build/en/guides/integrations-guide

Commands to uninstall an Astro integration, such as `@astrojs/react`, from your project using npm, pnpm, or Yarn.

```bash
npm uninstall @astrojs/react
```

```bash
pnpm remove @astrojs/react
```

```bash
yarn remove @astrojs/react
```

--------------------------------

### User Registration API

Source: https://v6.docs.astro.build/en/guides/backend/supabase

This endpoint allows for the registration of new users. It accepts a POST request with user credentials and utilizes the Supabase SDK to create a new user account.

```APIDOC
## POST /api/auth/register

### Description
Registers a new user with the provided email and password.

### Method
POST

### Endpoint
/api/auth/register

### Parameters
#### Request Body
- **email** (string) - Required - The email address of the user.
- **password** (string) - Required - The password for the new user.

### Request Example
```json
{
  "email": "user@example.com",
  "password": "securepassword"
}
```

### Response
#### Success Response (200)
Redirects to the sign-in page upon successful registration.

#### Error Response (400)
- **message** (string) - Email and password are required.

#### Error Response (500)
- **message** (string) - An error message from Supabase if registration fails.
```

--------------------------------

### JavaScript Code Block with Syntax Highlighting

Source: https://v6.docs.astro.build/en/guides/syntax-highlighting

An example of a JavaScript code block within a Markdown file, demonstrating syntax highlighting. Astro uses Shiki by default to style these blocks with inline styles.

```javascript
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l);
  return true;
};

```

--------------------------------

### Programmatic Prefetching with FIFO Strategy

Source: https://v6.docs.astro.build/en/guides/prefetch

Shows how to programmatically prefetch multiple links using a FIFO (First In, First Out) strategy with `eagerness: 'moderate'`. This approach leverages browser heuristics to manage prefetching for a large set of links, suitable for dynamic content or lists.

```html
<a class="link-moderate" href="/nice-link-1">A Nice Link 1</a>
<a class="link-moderate" href="/nice-link-2">A Nice Link 2</a>
<a class="link-moderate" href="/nice-link-3">A Nice Link 3</a>
<a class="link-moderate" href="/nice-link-4">A Nice Link 4</a>
...
<a class="link-moderate" href="/nice-link-20">A Nice Link 20</a>
```

```javascript
import { prefetch } from 'astro:prefetch';


const linkModerate = document.getElementsByClassName('link-moderate');
linkModerate.forEach((link) => prefetch(link.getAttribute('href'), {eagerness: 'moderate'}));
```

--------------------------------

### Configure session.driver in Astro

Source: https://v6.docs.astro.build/en/reference/configuration-reference

Specifies the driver to use for session storage. While some adapters provide a default driver, you can override it. This example shows configuring the Redis driver with its URL option.

```javascript
import { defineConfig, sessionDrivers } from 'astro/config'
import vercel from '@astrojs/vercel'


export default defineConfig({
  adapter: vercel()
  session: {
    driver: sessionDrivers.redis({
      url: process.env.REDIS_URL
    }),
  }
})
```

--------------------------------

### Basic Astro Page Structure

Source: https://v6.docs.astro.build/en/basics/astro-pages

An example of a basic Astro page using the `.astro` file extension. Astro pages must produce a full HTML document. Astro automatically adds `<!DOCTYPE html>` and `<head>` content if not explicitly included, unless marked as a partial page.

```astro
---
---
<html lang="en">
  <head>
    <title>My Homepage</title>
  </head>
  <body>
    <h1>Welcome to my website!</h1>
  </body>
</html>

```

--------------------------------

### Sort Astro Collection Entries

Source: https://v6.docs.astro.build/en/guides/content-collections

Shows how to sort entries fetched from an Astro collection. Since the default sort order is non-deterministic, this example demonstrates sorting blog posts by their publication date in descending order using the `.sort()` method.

```typescript
import { getCollection } from 'astro:content';


const posts = (await getCollection('blog')).sort(
  (a, b) => b.data.pubDate.valueOf() - a.data.pubDate.valueOf(),
);
```

--------------------------------

### Filter Collection Entries by Data Property (Astro)

Source: https://v6.docs.astro.build/en/guides/content-collections

This example shows how to filter entries from a collection using the `getCollection()` function with a callback. It specifically filters out blog entries where the `draft` property is set to `true`, ensuring only published posts are retrieved.

```javascript
// Example: Filter out content entries with `draft: true`
import { getCollection } from 'astro:content';
const publishedBlogEntries = await getCollection('blog', ({ data }) => {
  return data.draft !== true;
});
```

--------------------------------

### Format Files with Prettier (Yarn)

Source: https://v6.docs.astro.build/en/editor-setup

Uses Yarn to execute Prettier for formatting all files in the project directory. The `--write` option applies the formatting changes directly to the files.

```bash
yarn exec prettier . --write
```

--------------------------------

### Configure Amplify Build Settings for Yarn (Static)

Source: https://v6.docs.astro.build/en/guides/deploy/aws

Specifies the build process for an Astro static site using Yarn with AWS Amplify. It defines commands for installing dependencies, building the site, and managing cache.

```yaml
version: 1
frontend:
  phases:
    preBuild:
      commands:
        - yarn install
    build:
      commands:
        - yarn build
  artifacts:
    baseDirectory: /dist
    files:
      - '**/*'
  cache:
    paths:
      - node_modules/**/*
```

--------------------------------

### Updating Astro Config for Hybrid to Static Rendering Mode

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v5

This code example shows how to update your Astro configuration file (`astro.config.mjs`) after the removal of the `output: 'hybrid'` rendering mode in Astro v5.0. The previous hybrid behavior is now the default for the `'static'` mode.

```javascript
import { defineConfig } from "astro/config";


export default defineConfig({
  output: 'hybrid',
});
```

--------------------------------

### Configure Netlify Build Settings

Source: https://v6.docs.astro.build/en/guides/deploy/netlify

Defines the build command and publish directory for an Astro site in a `netlify.toml` file. This configuration is automatically read by Netlify for deployments.

```toml
[build]
  command = "npm run build"
  publish = "dist"
```

--------------------------------

### Configure Cloudinary Node.js SDK in Astro

Source: https://v6.docs.astro.build/en/guides/media/cloudinary

Demonstrates how to configure the Cloudinary Node.js SDK by setting environment variables in a `.env` file and initializing a Cloudinary instance within an Astro component. This enables interaction with Cloudinary APIs.

```javascript
PUBLIC_CLOUDINARY_CLOUD_NAME="<Your Cloud Name>"
PUBLIC_CLOUDINARY_API_KEY="<Your API Key>"
CLOUDINARY_API_SECRET="<Your API Secret>"

```

```javascript
---
import { v2 as cloudinary } from "cloudinary";


cloudinary.config({
  cloud_name: import.meta.env.PUBLIC_CLOUDINARY_CLOUD_NAME,
  api_key: import.meta.env.PUBLIC_CLOUDINARY_API_KEY,
  api_secret: import.meta.env.CLOUDINARY_API_SECRET,
});
---

```

--------------------------------

### GitHub Actions Workflow for AWS Deployment

Source: https://v6.docs.astro.build/en/guides/deploy/aws

This YAML workflow automates the build and deployment process for a website. It checks out the code, configures AWS credentials, installs dependencies, builds the application, deploys to S3, and invalidates CloudFront.

```yaml
name: Deploy Website

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      - name: Configure AWS Credentials
        uses: aws-actions/configure-aws-credentials@v1
        with:
          aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
          aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          aws-region: us-east-1
      - name: Install modules
        run: npm ci
      - name: Build application
        run: npm run build
      - name: Deploy to S3
        run: aws s3 sync --delete ./dist/ s3://${{ secrets.BUCKET_ID }}
      - name: Create CloudFront invalidation
        run: aws cloudfront create-invalidation --distribution-id ${{ secrets.DISTRIBUTION_ID }} --paths "/*"
```

--------------------------------

### Update TypeScript to v5.0

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v3

Install the latest version of TypeScript as a development dependency using npm. Astro v3.0 requires TypeScript v5.0 or higher.

```bash
npm install typescript@latest --save-dev
```

--------------------------------

### Carry over theme preference with astro:before-swap

Source: https://v6.docs.astro.build/en/guides/view-transitions

This example uses the 'astro:before-swap' event to ensure the browser's dark mode preference, stored in localStorage, is applied to the new page before the content is replaced.

```javascript
<script>
document.addEventListener("astro:before-swap", (event) => {
  event.newDocument.documentElement.dataset.theme =
    localStorage.getItem("darkMode") ? "dark" : "light";
});
</script>
```

--------------------------------

### Turso CLI: Create Database

Source: https://v6.docs.astro.build/en/guides/astro-db

Command to create a new database on Turso. Replace `[database-name]` with the desired name for your new database.

```bash
turso db create [database-name]
```

--------------------------------

### Get Session Data (API Context)

Source: https://v6.docs.astro.build/en/reference/api-reference

Retrieves a value from the session within an API route context. The `session` object is destructured from the `APIContext`.

```javascript
import type { APIContext } from 'astro';

export async function GET({ session }: APIContext) {
  const cart = await session.get('cart');
  return Response.json({ cart });
}
```

--------------------------------

### Astro Component Structure Example

Source: https://v6.docs.astro.build/en/basics/astro-components

Illustrates the basic structure of an Astro component, separating the component script (JavaScript) from the component template (HTML with JS expressions). The script is enclosed in a code fence (---).

```astro
---
// Component Script (JavaScript)
---
<!-- Component Template (HTML + JS Expressions) -->
```

--------------------------------

### Set Cache-Control Header in Astro

Source: https://v6.docs.astro.build/en/guides/on-demand-rendering

Illustrates how to set the `Cache-Control` header for a response using the `Astro.response.headers` object. This example sets a public cache with a max age of one hour.

```javascript
---
export const prerender = false; // Not needed in 'server' mode


Astro.response.headers.set('Cache-Control', 'public, max-age=3600');
---
<html>
  <!-- Page here... -->
</html>

```

--------------------------------

### Built-in Session Drivers

Source: https://v6.docs.astro.build/en/reference/session-driver-reference

Astro provides built-in session drivers that can be imported from `astro/config`. This example shows how to configure a Redis driver using an environment variable for the URL.

```APIDOC
## Built-in Session Drivers

### Description
Astro exports built-in session drivers from `astro/config`.

### Method
N/A (Configuration)

### Endpoint
N/A (Configuration)

### Parameters
#### Query Parameters
N/A

#### Request Body
N/A

### Request Example
```javascript
import { defineConfig, sessionDrivers } from 'astro/config'


export default defineConfig({
    session: {
        driver: sessionDrivers.redis({
            url: process.env.REDIS_URL
        }),
    }
})
```

### Response
N/A (Configuration)

#### Success Response (200)
N/A

#### Response Example
N/A
```

--------------------------------

### Execute Deno Deploy Script

Source: https://v6.docs.astro.build/en/guides/deploy/deno

Executes the 'deno-deploy' script defined in 'package.json' to build and deploy the Astro site to Deno Deploy in a single command.

```bash
npm run deno-deploy
```

--------------------------------

### Integrate htmx for Dynamic Updates

Source: https://v6.docs.astro.build/en/basics/astro-pages

This example shows how to use htmx to dynamically update a section of a page using an Astro partial. A button with `hx-post` attribute targets a partial's URL, and the returned HTML content replaces the content of the specified target element (`#parent-div`) using `innerHTML` swap.

```html
<html>
  <head>
    <title>My page</title>
    <script src="https://unpkg.com/htmx.org@1.9.6"
      integrity="sha384-FhXw7b6AlE/jyjlZH5iHa/tTe9EpJ1Y55RjcgPbjeWMskSxZt1v9qkxLJWNJaGni"
      crossorigin="anonymous"></script>
  </head>
  <body>
    <section>
      <div id="parent-div">Target here</div>


      <button hx-post="/partials/clicked/"
        hx-trigger="click"
        hx-target="#parent-div"
        hx-swap="innerHTML"
      >
        Click Me!
      </button>
    </section>
  </body>
</html>
```

--------------------------------

### Access Request Method in Astro

Source: https://v6.docs.astro.build/en/guides/on-demand-rendering

Shows how to retrieve the HTTP method of the incoming request using `Astro.request.method`. This property returns a string representing the method (e.g., 'GET').

```javascript
---
export const prerender = false; // Not needed in 'server' mode


console.log(Astro.request.method) // GET (when navigated to in the browser)
---

```

--------------------------------

### Programmatic Prefetching with Eagerness Control

Source: https://v6.docs.astro.build/en/guides/prefetch

Demonstrates how to use the `prefetch()` function to control the eagerness of resource prefetching, balancing performance benefits with resource costs.

```APIDOC
## Programmatic Prefetching with Eagerness Control

### Description
Use the `prefetch()` function from `astro:prefetch` to suggest to the browser how eagerly it should prefetch or prerender link targets. The `eagerness` option accepts `'immediate'`, `'eager'`, `'moderate'`, or `'conservative'` to balance prefetching benefits against resource consumption.

### Method
`prefetch(href: string, options?: { eagerness?: 'immediate' | 'eager' | 'moderate' | 'conservative' }): void`

### Endpoint
`astro:prefetch` (module import)

### Parameters
#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
import { prefetch } from 'astro:prefetch';

// Prefetch a resource-intensive page with conservative eagerness
prefetch('/data-heavy-dashboard', { eagerness: 'conservative' });

// Prefetch a critical page with default immediate eagerness
prefetch('/getting-started');

// Prefetch a less critical page with moderate eagerness
prefetch('/terms-of-service', { eagerness: 'moderate' });
```

### Response
#### Success Response (200)
N/A (This is a client-side function)

#### Response Example
N/A
```

--------------------------------

### On-demand API Endpoint with Random Number

Source: https://v6.docs.astro.build/en/guides/on-demand-rendering

An example of an API endpoint in Astro that is rendered on demand. It exports `prerender = false` and returns a random number in the response.

```javascript
export const prerender = false;


export async function GET() {
  let number = Math.random();
  return new Response(
    JSON.stringify({
      number,
      message: `Here's a random number: ${number}`,
    }),
  );
}
```

--------------------------------

### Create a Boolean Store with Nano Stores

Source: https://v6.docs.astro.build/en/recipes/sharing-state

Define a shared state using Nano Stores' `atom` function. This example creates a store named `isOpen` to track the boolean state of a dialog, initialized to `false`.

```javascript
import { atom } from 'nanostores';


export const isOpen = atom(false);
```

--------------------------------

### Supported Data Types

Source: https://v6.docs.astro.build/en/guides/environment-variables

Information on the four data types supported for environment variables: strings, numbers, enums, and booleans, with examples using `envField`.

```APIDOC
## Supported Data Types

### Description
This section outlines the data types supported for environment variables in Astro and provides examples of how to define them using `envField`.

### Supported Types
- **String**: `envField.string({ optional: true, default: "foo" })`
- **Number**: `envField.number({ optional: true, default: 15 })`
- **Boolean**: `envField.boolean({ optional: true, default: true })`
- **Enum**: `envField.enum({ values: ["foo", "bar", "baz"], optional: true, default: "baz" })`

Refer to the `envField` API reference for a complete list of validation fields.
```

--------------------------------

### Implement getSecret() with setGetEnv in Astro

Source: https://v6.docs.astro.build/en/reference/adapter-reference

This code snippet shows how to implement `getSecret()` using `setGetEnv` in an Astro server entrypoint. It imports `setGetEnv` from `astro/env/setup` and calls it with a function that retrieves environment variables. This setup is crucial for adapters supporting secrets, ensuring environment variables are accessible during request processing.

```JavaScript
import { App } from 'astro/app';
import { setGetEnv } from "astro/env/setup"


setGetEnv((key) => process.env[key])


export function createExports(manifest) {
  const app = new App(manifest);


  const handler = (event, context) => {
    // ...
  };


  return { handler };
}
```

--------------------------------

### Adapt Dynamic Routes for SSR in Astro

Source: https://v6.docs.astro.build/en/guides/routing

This example adapts the `[...slug]` dynamic routing for SSR by removing `getStaticPaths` and `props`. Instead, it looks up the slug parameter in an object and redirects to a 404 page if the slug is not found. This approach is necessary because SSR pages cannot use `getStaticPaths()` or receive props directly.

```astro
---
const pages = [
  {
    slug: undefined,
    title: 'Astro Store',
    text: 'Welcome to the Astro store!',
  },
  {
    slug: 'products',
    title: 'Astro products',
    text: 'We have lots of products for you',
  },
  {
    slug: 'products/astro-handbook',
    title: 'The ultimate Astro handbook',
    text: 'If you want to learn Astro, you must read this book.',
  }
];


const { slug } = Astro.params;
const page = pages.find((page) => page.slug === slug);
if (!page) return Astro.redirect("/404");
const { title, text } = page;
---
<html>
  <head>
    <title>{title}</title>
  </head>
  <body>
    <h1>{title}</h1>
    <p>{text}</p>
  </body>
</html>

```

--------------------------------

### Astro Image Component - Layout Examples

Source: https://v6.docs.astro.build/en/reference/modules/astro-assets

Shows various layout options for the Astro Image component, including overriding the default 'constrained' layout with 'full-width' and 'none'. The 'full-width' layout makes the image responsive to the container's width, while 'none' disables responsive image generation.

```astro
---
import { Image } from 'astro:assets';
import myImage from '../assets/my_image.png';
---
<Image src={myImage} alt="This will use constrained layout" width={800} height={600} />
<Image src={myImage} alt="This will use full-width layout" layout="full-width" />
<Image src={myImage} alt="This will disable responsive images" layout="none" />

```

--------------------------------

### Fetch Catalogue Paths with Crystallize GraphQL API and Astro

Source: https://v6.docs.astro.build/en/guides/cms/crystallize

This code snippet demonstrates how to initialize the Crystallize API client, define a GraphQL query to fetch catalogue paths, execute the query, and then render the results within an Astro component. It assumes the `@crystallize/js-api-client` library is installed.

```javascript
import BaseLayout from '../../layouts/BaseLayout.astro';
import { createClient } from '@crystallize/js-api-client';


const apiClient = createClient({
  tenantIdentifier: 'furniture'
});


const query = `
  query getCataloguePaths{
    catalogue(language: "en", path: "/shop") {
      name
      children {
        name
        path
      }
    }
  }
`
const { data: { catalogue } } = await apiClient.catalogueApi(query)
// ... rest of the Astro component
<BaseLayout>
  <h1>{catalogue.name}</h1>
  <nav>
    <ul>
      {catalogue.children.map(child => (
        <li><a href={child.path}>{child.name}</a></li>
      ))}
    </ul>
  </nav>
</BaseLayout>
```

--------------------------------

### Generate Dynamic Routes with getStaticPaths in Astro

Source: https://v6.docs.astro.build/en/reference/routing-reference

This example uses the `getStaticPaths()` function in Astro to dynamically generate multiple prerendered routes based on parameters. It returns an array of objects, each specifying `params` for a unique URL path, enabling static site generation for dynamic content.

```javascript
---
// In 'server' mode, opt in to prerendering:
// export const prerender = true


export async function getStaticPaths() {
  return [
    // { params: { /* required */ }, props: { /* optional */ } },
    { params: { post: '1' } }, // [post] is the parameter
    { params: { post: '2' } }, // must match the file name
    // ...
  ];
}
---
<!-- Your HTML template here. -->
```

--------------------------------

### Use astro:before-preparation to show loading spinner

Source: https://v6.docs.astro.build/en/guides/view-transitions

This event fires before content is loaded, allowing for actions like showing a loading spinner. It modifies the event's loader to include custom asynchronous logic for managing the spinner.

```javascript
<script is:inline>
document.addEventListener("astro:before-preparation", (event) => {
  const originalLoader = event.loader;
  event.loader = async function () {
    const { startSpinner } = await import("./spinner.js");
    const stop = startSpinner();
    await originalLoader();
    stop();
  };
});
</script>
```

--------------------------------

### Astro Component Usage with Props

Source: https://v6.docs.astro.build/en/basics/astro-components

Shows how to import and use an Astro component ('GreetingHeadline') in another Astro component or page, passing props as attributes. This demonstrates the mechanism for data flow between components.

```astro
---
import GreetingHeadline from './GreetingHeadline.astro';
const name = 'Astro';
---
<h1>Greeting Card</h1>
<GreetingHeadline greeting="Hi" name={name} />
<p>I hope you have a wonderful day!</p>

```

--------------------------------

### Access Request URL in Astro Endpoint

Source: https://v6.docs.astro.build/en/guides/endpoints

This snippet shows how to access the request URL within an Astro endpoint function. It uses the 'request' object provided to the GET function to extract the pathname, demonstrating how to get the current endpoint's URL.

```typescript
import type { APIRoute } from "astro";


export const GET: APIRoute = ({ params, request }) => {
  return new Response(
    JSON.stringify({
      path: new URL(request.url).pathname,
    }),
  );
};
```

--------------------------------

### Handle Live Collection Validation Errors in Astro

Source: https://v6.docs.astro.build/en/guides/content-collections

Illustrates how to handle validation errors when fetching live entries in Astro. It specifically checks for `LiveCollectionValidationError` and provides an example of rewriting the response upon encountering an error.

```typescript
---
export const prerender = false; // Not needed in 'server' mode


import { LiveCollectionValidationError } from 'astro/content/runtime';
import { getLiveEntry } from 'astro:content';


const { entry, error } = await getLiveEntry('products', '123');


// You can handle validation errors specifically
if (LiveCollectionValidationError.is(error)) {
  console.error(error.message);
  return Astro.rewrite('/500');
}


// TypeScript knows entry.data matches your Zod schema, not the loader's type
console.log(entry?.data.displayPrice); // e.g., "$29.99"
---

```

--------------------------------

### Apply Layout and Frontmatter to Astro Blog Post

Source: https://v6.docs.astro.build/en/tutorial/4-layouts/2

This is an example of YAML frontmatter for an Astro Markdown blog post. It specifies the layout file to use and provides data such as title, publication date, description, author, image URL, and tags. This data is then accessible within the associated layout component.

```markdown
---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'My First Blog Post'
pubDate: 2022-07-01
description: 'This is the first post of my new Astro blog.'
author: 'Astro Learner'
image:
    url: 'https://docs.astro.build/assets/rose.webp'
    alt: 'The Astro logo on a dark background with a pink glow.'
tags: ["astro", "blogging", "learning in public"]
---

```

--------------------------------

### Markdown Page with Layout and Frontmatter

Source: https://v6.docs.astro.build/en/basics/astro-pages

An example of a Markdown page (`.md`) used within an Astro project. It utilizes the `layout` frontmatter property to specify a layout component and includes frontmatter for metadata like the title.

```markdown
---
layout: ../layouts/MySiteLayout.astro
title: My Markdown page
---
# Title


This is my page, written in **Markdown.**

```

--------------------------------

### Alpine.js Collapse Plugin Usage in Astro

Source: https://v6.docs.astro.build/en/guides/integrations-guide/alpinejs

Demonstrates how to use Alpine.js directives and plugins within an Astro component. This example uses the Collapse plugin to toggle the visibility of a paragraph.

```html
---
---
<html>
  <head>
    <!-- ... -->
    <script defer src="https://cdn.jsdelivr.net/npm/@alpinejs/collapse@3.x.x/dist/cdn.min.js"></script>
  </head>
  <body>
    <!-- ... -->
    <div x-data="{ expanded: false }">
      <button @click="expanded = ! expanded">Toggle Content</button>


      <p id="foo" x-show="expanded" x-collapse>
        Lorem ipsum
      </p>
    </div>
  </body>
</html>
```

--------------------------------

### Dockerfile for Astro Static Site with NGINX

Source: https://v6.docs.astro.build/en/recipes/docker

This Dockerfile builds an Astro site in static mode and serves it using NGINX on port 8080. It includes steps to install dependencies, build the site, and configure NGINX to serve the static files.

```Dockerfile
FROM node:lts AS build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build


FROM nginx:alpine AS runtime
COPY ./nginx/nginx.conf /etc/nginx/nginx.conf
COPY --from=build /app/dist /usr/share/nginx/html
EXPOSE 8080
```

--------------------------------

### Get Session Data (Astro)

Source: https://v6.docs.astro.build/en/reference/api-reference

Retrieves a value from the session using its key. Returns `undefined` if the key does not exist. This is typically used within Astro components.

```javascript
const cart = await Astro.session?.get('cart');
```

--------------------------------

### Create a 404 Not Found Page in Astro

Source: https://v6.docs.astro.build/en/guides/cms/storyblok

A simple Astro component to display a 'Not found' message when a requested page does not exist. This is used as a fallback for on-demand rendering.

```astro
<html lang="en">
  <head>
    <title>Not found</title>
  </head>
  <body>
    <p>Sorry, this page does not exist.</p>
  </body>
</html>

```

--------------------------------

### Configure ButterCMS API Token in Astro

Source: https://v6.docs.astro.build/en/guides/cms/buttercms

Sets up the ButterCMS API token as an environment variable in an Astro project's .env file for authentication.

```env
BUTTER_TOKEN=YOUR_API_TOKEN_HERE
```

--------------------------------

### Initialize Ghost Content API Client

Source: https://v6.docs.astro.build/en/guides/cms/ghost

Initialize the Ghost Content API client in a ghost.ts file located in your Astro project's lib directory. This client instance is used to fetch data from your Ghost site using your Content API key.

```typescript
import GhostContentAPI from '@tryghost/content-api';


// Create API instance with site credentials
export const ghostClient = new GhostContentAPI({
    url: 'http://127.0.0.1:2368', // This is the default URL if your site is running on a local environment
    key: import.meta.env.CONTENT_API_KEY,
    version: 'v5.0',
});
```

--------------------------------

### Custom Prerendered Error Page Fetching in JavaScript

Source: https://v6.docs.astro.build/en/reference/adapter-reference

This example shows how to override the default error page fetching behavior in Astro. It reads '500.html' and '404.html' from the file system instead of making HTTP requests, providing custom responses for server errors and not found pages.

```javascript
return app.render(request, {
  prerenderedErrorPageFetch: async (url: string): Promise<Response> => {
    if (url.includes("/500")) {
      const content = await fs.promises.readFile("500.html", "utf-8");
      return new Response(content, {
        status: 500,
        headers: { "Content-Type": "text/html" },
      });
    }


    const content = await fs.promises.readFile("404.html", "utf-8");
    return new Response(content, {
      status: 404,
      headers: { "Content-Type": "text/html" },
    });
  }
});
```

--------------------------------

### Build Astro Site (Yarn)

Source: https://v6.docs.astro.build/en/guides/deploy/deno

Builds the Astro project for production using Yarn. This command generates the static or server-rendered output in the `dist` directory.

```bash
yarn run build
```

--------------------------------

### Create a remark plugin to modify frontmatter in Astro

Source: https://v6.docs.astro.build/en/guides/markdown-content

This example defines a remark plugin function that programmatically adds a 'customProperty' to the frontmatter of Markdown or MDX files. The plugin modifies the `file.data.astro.frontmatter` object.

```javascript
export function exampleRemarkPlugin() {
  // All remark and rehype plugins return a separate function
  return function (tree, file) {
    file.data.astro.frontmatter.customProperty = 'Generated property';
  }
}
```

--------------------------------

### Import YAML Data in Astro

Source: https://v6.docs.astro.build/en/recipes/add-yaml-support

Demonstrates how to import YAML data directly into an Astro component or module using a standard import statement. This functionality is enabled after configuring the Rollup YAML plugin.

```javascript
import yml from './data.yml';
```

--------------------------------

### Handle File Extensions in Imports

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

In Astro v0.21+, files must be referenced by their exact file extension. This applies to both JavaScript/TypeScript files and CSS preprocessor files.

```javascript
import Div from './Div.jsx' // Astro v0.20
import Div from './Div.tsx' // Astro v0.21
```

```html
<link rel="stylesheet" href={Astro.resolve('./Div.css')}>
<link rel="stylesheet" href={Astro.resolve('./Div.scss')}>
```

--------------------------------

### Configure Netlify Adapter for Static Sites with Redirects

Source: https://v6.docs.astro.build/en/guides/integrations-guide/netlify

For static Astro sites deployed on Netlify, the adapter can translate Astro's `redirects` configuration into Netlify's `_redirects` file format. This enables server-side routing for static deployments.

```javascript
import { defineConfig } from 'astro/config';
import netlify from '@astrojs/netlify';


export default defineConfig({
  // ...
  adapter: netlify(),
  redirects: {
    '/blog/old-post': '/blog/new-post',
  },
});
```

--------------------------------

### Configure Astro to Use Rollup YAML Plugin

Source: https://v6.docs.astro.build/en/recipes/add-yaml-support

Configures the `astro.config.mjs` file to include the `@rollup/plugin-yaml` plugin in the Vite configuration. This step enables Astro to process YAML imports.

```javascript
import {
  defineConfig
} from 'astro/config';
import yaml from '@rollup/plugin-yaml';


export default defineConfig({
  vite: {
    plugins: [yaml()]
  }
});
```

--------------------------------

### Generate Dynamic Pages with getStaticPaths in Astro

Source: https://v6.docs.astro.build/en/guides/routing

This example demonstrates how to use `getStaticPaths` with a rest parameter (`[...slug]`) to generate static pages for slugs of varying depths. It maps an array of page data to route parameters and props, enabling dynamic page creation.

```astro
---
export function getStaticPaths() {
  const pages = [
    {
      slug: undefined,
      title: "Astro Store",
      text: "Welcome to the Astro store!",
    },
    {
      slug: "products",
      title: "Astro products",
      text: "We have lots of products for you",
    },
    {
      slug: "products/astro-handbook",
      title: "The ultimate Astro handbook",
      text: "If you want to learn Astro, you must read this book.",
    },
  ];


  return pages.map(({ slug, title, text }) => {
    return {
      params: { slug },
      props: { title, text },
    };
  });
}


const { title, text } = Astro.props;
---
<html>
  <head>
    <title>{title}</title>
  </head>
  <body>
    <h1>{title}</h1>
    <p>{text}</p>
  </body>
</html>

```

--------------------------------

### Apply Font Family using CSS Variable

Source: https://v6.docs.astro.build/en/reference/experimental-flags/fonts

This CSS example demonstrates how to apply a font family using a CSS variable, which is typically set up by Astro's Fonts API. This allows for consistent font application across styles.

```css
body {
    font-family: var(--font-roboto);
}
```

--------------------------------

### User Sign-in API

Source: https://v6.docs.astro.build/en/guides/backend/supabase

This endpoint handles user sign-in. It accepts a POST request with user credentials and uses the Supabase SDK to authenticate the user and set session cookies.

```APIDOC
## POST /api/auth/signin

### Description
Signs in an existing user with the provided email and password. Sets authentication cookies upon successful sign-in.

### Method
POST

### Endpoint
/api/auth/signin

### Parameters
#### Request Body
- **email** (string) - Required - The email address of the user.
- **password** (string) - Required - The password of the user.

### Request Example
```json
{
  "email": "user@example.com",
  "password": "securepassword"
}
```

### Response
#### Success Response (200)
Redirects to the dashboard upon successful sign-in. Sets `sb-access-token` and `sb-refresh-token` cookies.

#### Error Response (400)
- **message** (string) - Email and password are required.

#### Error Response (500)
- **message** (string) - An error message from Supabase if sign-in fails.
```

--------------------------------

### Define a Server Action with Input Validation

Source: https://v6.docs.astro.build/en/reference/modules/astro-actions

Demonstrates how to define a server action using `defineAction`. This example includes input validation using Zod for a 'name' string and a simple handler that returns a greeting.

```typescript
import { defineAction } from 'astro:actions';
import { z } from 'astro/zod';


export const server = {
  getGreeting: defineAction({
    input: z.object({
      name: z.string(),
    }),
    handler: async (input, context) => {
      return `Hello, ${input.name}!`
    }
  })
}
```

--------------------------------

### Configure Adapter Exports in Astro Integration (JavaScript)

Source: https://v6.docs.astro.build/en/reference/adapter-reference

This snippet demonstrates how to configure the adapter's server entrypoint and expected exports within an Astro integration using `setAdapter`.

```javascript
export default function createIntegration() {
  return {
    name: '@example/my-adapter',
    hooks: {
      'astro:config:done': ({ setAdapter }) => {
        setAdapter({
          name: '@example/my-adapter',
          serverEntrypoint: '@example/my-adapter/server.js',
          exports: ['handler'],
        });
      },
    },
  };
}
```

--------------------------------

### Login to Azion CLI

Source: https://v6.docs.astro.build/en/guides/deploy/azion

Authenticates your Azion CLI with your Azion account. This is a prerequisite for using most Azion CLI commands for deployment and management.

```bash
azion login
```

--------------------------------

### Fetch and Display Shop Items in Astro

Source: https://v6.docs.astro.build/en/guides/cms/buttercms

Fetches a collection of 'shopitem' data using the ButterCMS SDK and renders it within an Astro component, handling HTML descriptions.

```astro
---
import { butterClient } from "../lib/buttercms";
const response = await butterClient.content.retrieve(["shopitem"]);


interface ShopItem {
  name: string,
  price: number,
  description: string,
}


const items = response.data.data.shopitem as ShopItem[];
---
<body>
  {items.map(item => <div>
    <h2>{item.name} - ${item.price}</h2>
    <p set:html={item.description}></p>
  </div>)}
</body>
```

--------------------------------

### Add Static Deno Deploy Script to package.json

Source: https://v6.docs.astro.build/en/guides/deploy/deno

Adds a 'deno-deploy' script to the 'package.json' file that builds the Astro site and then deploys it as a static site to Deno Deploy.

```json
{
  // ...
  "scripts": {
  "dev": "astro dev",
  "start": "astro dev",
  "build": "astro build",
  "preview": "astro preview",
  "deno-deploy": "npm run build && cd dist && deployctl deploy jsr:@std/http/file-server"
  }
}
```

--------------------------------

### Render Blog Post Content with a Layout (Astro)

Source: https://v6.docs.astro.build/en/tutorial/6-islands/4

This code extends the previous snippet by rendering the blog post content within a specified layout (`MarkdownPostLayout.astro`). This allows for a consistent design across all blog posts. It fetches posts using `getCollection()`, renders the content, and then wraps it in the chosen layout, passing frontmatter data to the layout.

```astro
---
import { getCollection, render } from 'astro:content';
import MarkdownPostLayout from '../../layouts/MarkdownPostLayout.astro';


export async function getStaticPaths() {
  const posts = await getCollection('blog');
  return posts.map(post => ({
    params: { slug: post.id }, props: { post },
  }));
}


const { post } = Astro.props;
const { Content } = await render(post);
---
<MarkdownPostLayout frontmatter={post.data}>
  <Content />
</MarkdownPostLayout>
```

--------------------------------

### NGINX Configuration for Astro Static Site

Source: https://v6.docs.astro.build/en/recipes/docker

This is a sample NGINX configuration file used to serve an Astro static site. It listens on port 8080, sets the document root, and configures gzip compression and error page handling.

```nginx
worker_processes  1;


events {
  worker_connections  1024;
}


http {
  server {
    listen 8080;
    server_name   _;


    root   /usr/share/nginx/html;
    index  index.html index.htm;
    include /etc/nginx/mime.types;


    gzip on;
    gzip_min_length 1000;
    gzip_proxied expired no-cache no-store private auth;
    gzip_types text/plain text/css application/json application/javascript application/x-javascript text/xml application/xml application/xml+rss text/javascript;


    error_page 404 /404.html;
    location = /404.html {
            root /usr/share/nginx/html;
            internal;
    }


    location / {
            try_files $uri $uri/index.html =404;
    }
  }
}
```

--------------------------------

### On-Demand Dynamic Routes with Rest Parameter in Astro

Source: https://v6.docs.astro.build/en/guides/routing

This example shows how to configure on-demand dynamic routes using a rest parameter (`[...slug]`) for adapters. It highlights that `getStaticPaths` should not be used for on-demand routes, as they serve any matching route dynamically. Only one rest parameter is permitted per file name.

```astro
---
export const prerender = false; // Not needed in 'server' mode
const { resource, id } = Astro.params;
---
<h1>{resource}: {id}</h1>

```

--------------------------------

### Create and Configure Select Element

Source: https://v6.docs.astro.build/en/reference/dev-toolbar-app-reference

Provides an example of creating an `astro-dev-toolbar-select` component, defining its options, and attaching a change event listener. The `selectStyle` property can be used to customize the appearance.

```javascript
const mySelect = document.createElement("astro-dev-toolbar-select");
const options = [
  { label: "First option", value: "first" },
  { label: "Second option", value: "second", isDefault: true },
];
const myOptions = options.map((option) => {
  const optionEl = document.createElement("option");
  optionEl.textContent = option.label;
  optionEl.setAttribute("value", option.value);
  optionEl.selected = option.isDefault || false;
  return optionEl;
});


mySelect.selectStyle = "green";
mySelect.append(...myOptions);

mySelect.element.addEventListener("change", (evt) => {
  if (evt.currentTarget instanceof HTMLSelectElement) {
    console.log(`The select value is now ${evt.currentTarget.value}!`);
  }
});
```

--------------------------------

### Static API Endpoint in 'server' Output Mode

Source: https://v6.docs.astro.build/en/guides/on-demand-rendering

An example of an API endpoint in Astro that is configured to be statically prerendered, even when the project's output mode is set to 'server'. It exports `prerender = true`.

```javascript
export const prerender = true;


export async function GET() {
  return new Response(
    JSON.stringify({
      message: `This is my static endpoint`,
    }),
  );
}
```

--------------------------------

### Check Local Node.js Version

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v2

Command to check the currently installed version of Node.js on your local development machine. This is crucial for ensuring compatibility with Astro v2.0, which requires Node.js 16.12.0 or later.

```bash
node -v
```

--------------------------------

### Configure remark-rehype Options in Astro

Source: https://v6.docs.astro.build/en/reference/configuration-reference

Pass custom options to the `remark-rehype` processor within Astro's markdown configuration. This example shows how to set custom labels for footnotes.

```javascript
export default defineConfig({
  markdown: {
    remarkRehype: {
      footnoteLabel: "Footnotes",
      footnoteBackLabel: "Back to reference 1",
    },
  },
});
```

--------------------------------

### On-Demand Rendering of Blog Pages with Storyblok in Astro

Source: https://v6.docs.astro.build/en/guides/cms/storyblok

Fetches blog page data from Storyblok based on the dynamic 'slug' parameter for on-demand rendering. Includes a fallback to a 404 page if the story is not found.

```astro
---
import { useStoryblokApi } from '@storyblok/astro'
import StoryblokComponent from '@storyblok/astro/StoryblokComponent.astro'
const storyblokApi = useStoryblokApi()
const slug = Astro.params.slug;
let content;
try {
  const { data } = await storyblokApi.get(`cdn/stories/blog/${slug}`, {
    version: import.meta.env.DEV ? "draft" : "published",
  });
  content = data.story.content
} catch (error) {
  return Astro.redirect('/404')
}
---
<html lang="en">
  <head>
    <title>Storyblok & Astro</title>
  </head>
  <body>
    <StoryblokComponent blok={content} />
  </body>
</html>

```

--------------------------------

### HookParameters Utility

Source: https://v6.docs.astro.build/en/reference/integrations-reference

A utility type to get the arguments type for a given Astro hook.

```APIDOC
## HookParameters

### Description
You can get the type of a hook’s arguments by passing the hook’s name to the `HookParameters` utility type.

### Example Usage
```typescript
import type { HookParameters } from 'astro';

function mySetup(options: HookParameters<'astro:config:setup'>) {
  options.updateConfig({ /* ... */ });
}
```
```

--------------------------------

### Configure TinaCMS Schema for Astro

Source: https://v6.docs.astro.build/en/guides/cms/tina-cms

Sets up the TinaCMS schema, defining collections, fields, and content structure for your Astro project. This example adds a 'posted' date field to posts.

```typescript
import { defineConfig } from "tinacms";


// Your hosting provider likely exposes this as an environment variable
const branch = process.env.HEAD || process.env.VERCEL_GIT_COMMIT_REF || "main";


export default defineConfig({
  branch,
  clientId: null, // Get this from tina.io
  token: null, // Get this from tina.io
  build: {
    outputFolder: "admin",
    publicFolder: "public",
  },
  media: {
    tina: {
      mediaRoot: "images",
      publicFolder: "public",
    },
  },
  schema: {
    collections: [
      {
        name: "posts",
        label: "Posts",
        path: "src/content/posts",
        format: 'mdx',
        fields: [
          {
            type: "string",
            name: "title",
            label: "Title",
            isTitle: true,
            required: true,
          },
          {
            type: "datetime",
            name: "posted",
            label: "Date Posted",
            required: true,
          },
          {
            type: "rich-text",
            name: "body",
            label: "Body",
            isBody: true,
          },
        ],
      },
    ],
  },
});
```

--------------------------------

### Manually Add Server and Client Renderers to Astro Container

Source: https://v6.docs.astro.build/en/reference/container-reference

This example demonstrates how to manually import and add server and client renderers for Vue, MDX, and React components to an Astro container. Server renderers are added first, followed by client renderers, ensuring proper rendering and hydration.

```javascript
import reactRenderer from "@astrojs/react/server.js";
import vueRenderer from "@astrojs/vue/server.js";
import mdxRenderer from "@astrojs/mdx/server.js";


const container = await experimental_AstroContainer.create();
container.addServerRenderer({ renderer: vueRenderer });
container.addServerRenderer({ renderer: mdxRenderer });


container.addServerRenderer({ renderer: reactRenderer });
container.addClientRenderer({ name: "@astrojs/react", entrypoint: "@astrojs/react/client.js" });
```

--------------------------------

### Display Astro CLI Help with npm, pnpm, or Yarn

Source: https://v6.docs.astro.build/en/reference/cli-reference

Displays a list of all available Astro CLI commands and global flags. This is useful for understanding the full range of functionalities and options. It can be invoked using npm, pnpm, or Yarn.

```bash
npx astro --help
```

```bash
pnpm astro --help
```

```bash
yarn astro --help
```

--------------------------------

### Fetch and Display Blog Posts in Astro

Source: https://v6.docs.astro.build/en/guides/cms/ghost

Fetches all blog posts from Ghost CMS using the ghostClient and displays them as a list of links on an Astro page. It imports the ghostClient from a local library and uses the posts.browse() method to retrieve post data.

```astro
--- 
import { ghostClient } from '../lib/ghost';
const posts = await ghostClient.posts
    .browse({
        limit: 'all',
    })
    .catch((err) => {
        console.error(err);
    });
---


<html lang="en">
    <head>
        <title>Astro + Ghost 👻</title>
    </head>
    <body>


        {
            posts.map((post) => (
                <a href={`/post/${post.slug}`}>
                    <h1> {post.title} </h1>
                </a>
            ))
        }
    </body>
</html>
```

--------------------------------

### Access Vite Configuration in Astro Integration

Source: https://v6.docs.astro.build/en/reference/integrations-reference

Allows access to the Vite configuration used in the build process. Useful for integrating custom logic within Astro's build setup.

```javascript
export default {
  name: 'my-integration',
  hooks: {
    'astro:build:setup': ({ vite }) => {
      const { publicDir, root } = vite;
    },
  }
}
```

--------------------------------

### Custom Font Provider for Private Registry in Astro

Source: https://v6.docs.astro.build/en/reference/experimental-flags/fonts

Implements a custom font provider for a private registry in Astro. This example demonstrates how to define a provider with initialization, font listing, and font resolution logic. It requires a utility function `retrieveFonts` and accepts a configuration object with an authentication token.

```typescript
import type { FontProvider } from "astro";
import { retrieveFonts, type Fonts } from "./utils.js";


interface Config {
  token: string;
}


export function registryFontProvider(config: Config): FontProvider {
  let data: Fonts = {}


  return {
    name: "registry",
    config,
    init: async () => {
      data = await retrieveFonts(token);
    },
    listFonts: () => {
      return Object.keys(data);
    },
    resolveFont: ({ familyName, ...options }) => {
      const fonts = data[familyName];
      if (fonts) {
        return { fonts };
      }
      return undefined;
    },
  };
}
```

```typescript
import { defineConfig } from "astro/config";
import { registryFontProvider } from "./font-provider";


export default defineConfig({
    experimental: {
        fonts: [{
            provider: registryFontProvider({
              token: "..."
            }),
            name: "Custom",
            cssVariable: "--font-custom"
        }]
    }
});
```

--------------------------------

### Using Params

Source: https://v6.docs.astro.build/en/reference/api-reference

Explains how to access dynamic route parameters using the `params` object.

```APIDOC
## Using Params

### Description
The `params` object provides access to the values of dynamic route segments. The keys in this object correspond to the parameter names in your file path.

### Example 1: Accessing Params in a Static Route
```astro
---
export function getStaticPaths() {
  return [
    { params: { id: '1' } },
    { params: { id: '2' } },
    { params: { id: '3' } }
  ];
}
const { id } = Astro.params;
---
<h1>{id}</h1>
```

### Example 2: Accessing Params in an Endpoint Function
```astro
---
import type { APIContext } from 'astro';

export function getStaticPaths() {
  return [
    { params: { id: '1' } },
    { params: { id: '2' } },
    { params: { id: '3' } }
  ];
}

export function GET({ params }: APIContext) {
  return new Response(
    JSON.stringify({ id: params.id }),
  );
}
```

### Example 3: Using Params for Data Fetching
```astro
---
import { getPost } from '../api';

const post = await getPost(Astro.params.id);

// No posts found with this ID
if (!post) {
  return Astro.redirect("/404")
}
---
<html>
  <h1>{post.name}</h1>
</html>
```
```

--------------------------------

### Specify Font Weights (JavaScript)

Source: https://v6.docs.astro.build/en/reference/experimental-flags/fonts

Example of configuring specific font weights for a font. This allows for selective downloading of font files, improving performance. It supports individual weights or ranges for variable fonts.

```javascript
weights: [200, "400", "bold"]
```

```javascript
weights: ["100 900"]
```

--------------------------------

### Using Astro Layout on an Index Page

Source: https://v6.docs.astro.build/en/tutorial/4-layouts/1

This Astro component demonstrates how to use a layout component (`BaseLayout`) on an index page. It imports the layout and wraps child content within the layout's tags. This allows for content specific to the index page to be rendered within the shared layout structure.

```astro
---
import BaseLayout from '../layouts/BaseLayout.astro';
const pageTitle = "Home Page";
---
<BaseLayout>
  <h2>My awesome blog subtitle</h2>
</BaseLayout>

```

--------------------------------

### Create Contentful Client in Astro

Source: https://v6.docs.astro.build/en/guides/cms/contentful

Initialize the Contentful client in Astro using the SDK and environment variables. This client is configured to use preview tokens and hosts for development and production environments.

```typescript
import * as contentful from "contentful";


export const contentfulClient = contentful.createClient({
  space: import.meta.env.CONTENTFUL_SPACE_ID,
  accessToken: import.meta.env.DEV
    ? import.meta.env.CONTENTFUL_PREVIEW_TOKEN
    : import.meta.env.CONTENTFUL_DELIVERY_TOKEN,
  host: import.meta.env.DEV ? "preview.contentful.com" : "cdn.contentful.com",
});
```

--------------------------------

### Accessing Complex Middleware Locals in Astro Component (Astro)

Source: https://v6.docs.astro.build/en/guides/middleware

Illustrates accessing complex data, including a function call and iterating over an array, from `Astro.locals` within an Astro component. This example shows how to use middleware-provided data for dynamic content generation.

```astro
---
const title = Astro.locals.welcomeTitle();
const orders = Array.from(Astro.locals.orders.entries());
const data = Astro.locals;
---
<h1>{title}</h1>
<p>This {data.property} is from middleware.</p>
<ul>
    {orders.map(order => {
        return <li>{/* do something with each order */}</li>;
    })}
</ul>
```

--------------------------------

### Customize remark and rehype plugins in Astro

Source: https://v6.docs.astro.build/en/guides/markdown-content

This example shows how to customize remark and rehype plugins by providing an options object in a nested array. It configures `remarkToc` with a 'contents' heading and `rehype-autolink-headings` to append anchor tags.

```javascript
import remarkToc from 'remark-toc';
import rehypeSlug from 'rehype-slug';
import rehypeAutolinkHeadings from 'rehype-autolink-headings';


export default {
  markdown: {
    remarkPlugins: [ [remarkToc, { heading: "contents"} ] ],
    rehypePlugins: [rehypeSlug, [rehypeAutolinkHeadings, { behavior: 'append' }]],
  },
}
```

--------------------------------

### nodeApp.headersMap

Source: https://v6.docs.astro.build/en/reference/adapter-reference

An array containing headers configuration, mapping pathnames to headers for specific routes.

```APIDOC
## nodeApp.headersMap

### Description
An array containing the headers configuration. Each entry maps a pathname to a list of headers that should be applied for that route. This is useful for applying headers such as CSP directives to prerendered routes.

### Property
`nodeApp.headersMap: NodeAppHeadersJson | undefined`

### Type
`NodeAppHeadersJson | undefined`

### Default Value
`undefined`
```

--------------------------------

### Generate Static Blog Post Paths in Astro

Source: https://v6.docs.astro.build/en/guides/cms/flotiq

Implement `getStaticPaths` in Astro to define routes for individual blog posts. This function fetches all blog post slugs from Flotiq and returns them as parameters for generating static pages.

```astro
---
import type { Blogpost } from "flotiq-api-ts";
import { flotiq } from "../../lib/flotiq";


export async function getStaticPaths() {
  const posts = await flotiq.BlogpostAPI.list();
  return posts.data?.map((post) => ({
    params: { slug: post.slug },
    props: post
  })) || []
}
---

```

--------------------------------

### Upgrade Astro and Integrations using pnpm

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v3

Update Astro to the latest version and install the latest versions of Astro integrations like React and Tailwind using pnpm. This ensures compatibility with Astro v3.x.

```bash
# Upgrade to Astro v3.x
pnpm add astro@latest

# Example: upgrade React and Tailwind integrations
pnpm add @astrojs/react@latest @astrojs/tailwind@latest
```

--------------------------------

### Correct Astro Component Rendering Syntax

Source: https://v6.docs.astro.build/en/reference/errors/invalid-component-args

Demonstrates the correct way to render Astro components using JSX-like syntax. This avoids errors caused by attempting to call components as functions. The examples show both single component rendering and mapping over an array to render multiple components.

```javascript
// Correct syntax for a single component
<MyAstroComponent prop1="value1" />

// Correct syntax for mapping over an array
{items.map(item => <MyAstroComponent {...item} />)}
```

--------------------------------

### Create a New Blog Post Markdown File in Astro

Source: https://v6.docs.astro.build/en/tutorial/5-astro-api/1

This example shows the frontmatter structure for a new Markdown blog post in Astro. It includes essential properties like layout, title, author, description, image, publication date, and tags, which are used by `import.meta.glob()` to generate the post list.

```markdown
---
layout: ../../layouts/MarkdownPostLayout.astro
title: My Fourth Blog Post
author: Astro Learner
description: "This post will show up on its own!"
image:
    url: "https://docs.astro.build/default-og-image.png"
    alt: "The word astro against an illustration of planets and stars."
pubDate: 2022-08-08
tags: ["astro", "successes"]
---
This post should show up with my other blog posts, because `import.meta.glob()` is returning a list of all my posts in order to create my list.
```

--------------------------------

### Load Nested JSON Collections with Custom Parser (JavaScript)

Source: https://v6.docs.astro.build/en/guides/content-collections

Explains how to use the `parser` argument with the `file()` loader to extract specific collections from a single, nested JSON document. This example shows how to separate 'dogs' and 'cats' collections from a 'pets.json' file.

```javascript
import { file } from "astro/loaders";
import { defineCollection } from "astro:content";


const dogs = defineCollection({
  loader: file("src/data/pets.json", { parser: (text) => JSON.parse(text).dogs })
});
const cats = defineCollection({
  loader: file("src/data/pets.json", { parser: (text) => JSON.parse(text).cats })
});

```

--------------------------------

### Define Live Content Collection with Custom Loader (Astro/TypeScript)

Source: https://v6.docs.astro.build/en/guides/content-collections

Demonstrates how to define a live content collection in Astro using `defineLiveCollection` and a custom `storeLoader`. It configures the loader with API credentials and an endpoint, and exports the collection for use in the application. This approach is suitable for integrating with external data sources that require runtime fetching.

```typescript
// Define live collections for accessing real-time data
import { defineLiveCollection } from 'astro:content';
import { storeLoader } from '@mystore/astro-loader';


const products = defineLiveCollection({
  loader: storeLoader({
    apiKey: process.env.STORE_API_KEY,
    endpoint: 'https://api.mystore.com/v1',
  }),
});


// Export a single `collections` object to register your collection(s)
export const collections = { products };

```

--------------------------------

### Nest Framework Components with Children (Astro)

Source: https://v6.docs.astro.build/en/guides/framework-components

Demonstrates nesting multiple framework components within an Astro file, including passing children to them. This example nests a React sidebar (`MyReactSidebar`) which itself contains React (`MyReactButton`) and Svelte (`MySvelteButton`) components within a named slot.

```astro
---
import MyReactSidebar from '../components/MyReactSidebar.jsx';
import MyReactButton from '../components/MyReactButton.jsx';
import MySvelteButton from '../components/MySvelteButton.svelte';
---
<MyReactSidebar>
  <p>Here is a sidebar with some text and a button.</p>
  <div slot="actions">
    <MyReactButton client:idle />
    <MySvelteButton client:idle />
  </div>
</MyReactSidebar>

```

--------------------------------

### Using Nested Layout with Transferred Slots

Source: https://v6.docs.astro.build/en/basics/astro-components

An example of using a nested layout where named slots are passed through to the base layout. This allows injecting content like `<title>` into the parent's `<slot name='head'>`.

```astro
import HomeLayout from '../layouts/HomeLayout.astro';
---
<HomeLayout>
  <title slot="head">Astro</title>
  <h1>Astro</h1>
</HomeLayout>

```

--------------------------------

### Create a Playwright Test for Page Meta

Source: https://v6.docs.astro.build/en/guides/testing

Create a Playwright test file (e.g., `src/test/index.spec.ts`) to verify page meta information. This example tests the page title by navigating to the specified URL and asserting the title.

```typescript
import { test, expect } from '@playwright/test';


test('meta is correct', async ({ page }) => {
  await page.goto("http://localhost:4321/");


  await expect(page).toHaveTitle('Astro is awesome!');
});
```

--------------------------------

### Deploy Astro Site to Surge

Source: https://v6.docs.astro.build/en/guides/deploy/surge

Deploys the built Astro site to Surge. The `dist` directory, containing the production-ready static files, is specified as the source for deployment. This command initiates the upload process to Surge's hosting infrastructure.

```bash
surge dist
```

--------------------------------

### Set Environment Variables for Static Deployment with npm

Source: https://v6.docs.astro.build/en/guides/deploy/clever-cloud

Configures the build environment for a static Astro application using npm. It sets the post-build hook to run the build command, and the pre-build hook to install dependencies and disable Astro telemetry. The webroot is set to '/dist'.

```bash
CC_POST_BUILD_HOOK="npm run build"
CC_PRE_BUILD_HOOK="npm install && npm run astro telemetry disable"
CC_WEBROOT="/dist"
```

--------------------------------

### Access Variables in Markdoc Content

Source: https://v6.docs.astro.build/en/guides/integrations-guide/markdoc

Access variables passed to the `Content` component within your Markdoc files using the `$` prefix. For example, `$abTestGroup`.

```markdoc
{% if $abTestGroup === 'image-optimization-lover' %}


Let me tell you about image optimization...


{% /if %}

```

--------------------------------

### Map and Format Blog Post Data for Preview (Astro/TypeScript)

Source: https://v6.docs.astro.build/en/guides/cms/contentful

Maps the fetched Contentful blog post entries to a new array (`posts`) with a simplified structure suitable for previews. It also reformats the date to a more readable string format.

```astro
---
import { contentfulClient } from "../lib/contentful";
import type { BlogPost } from "../lib/contentful";


const entries = await contentfulClient.getEntries<BlogPost>({
  content_type: "blogPost",
});


const posts = entries.items.map((item) => {
  const { title, date, description, slug } = item.fields;
  return {
    title,
    slug,
    description,
    date: new Date(date).toLocaleDateString()
  };
});
---

```

--------------------------------

### Static File Endpoints - Basic GET Request

Source: https://v6.docs.astro.build/en/guides/endpoints

Defines a static file endpoint that generates a JSON response. The file name determines the endpoint URL and the file extension.

```APIDOC
## POST /data.json

### Description
This endpoint generates a static JSON file at `/data.json` containing project information.

### Method
GET

### Endpoint
`/data.json`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
None

### Response
#### Success Response (200)
- **name** (string) - The name of the project.
- **url** (string) - The URL of the project.

#### Response Example
```json
{
  "name": "Astro",
  "url": "https://astro.build/"
}
```
```

--------------------------------

### Generate Blog Post Pages with Astro and Cosmic

Source: https://v6.docs.astro.build/en/guides/cms/cosmic

This Astro component dynamically generates individual blog post pages. It uses `getStaticPaths` to fetch all posts from Cosmic and create routes based on each post's slug. The post data is then passed as props to render the title, author, cover image, and rich text content.

```astro
---
import { getAllPosts } from '../../lib/cosmic'
import { Image } from 'astro:assets'


export async function getStaticPaths() {
  const data = (await getAllPosts()) || []


  return data.map((post) => {
    return {
      params: { slug: post.slug },
      props: { post }
    }
  })
}


const { post } = Astro.props
---


<article class="mx-auto max-w-screen-md pt-20">
  <section class="border-b pb-8">
    <h1 class="text-4xl font-bold">{post.title}</h1>
    <div class="my-4"></div>
    <span class="text-sm font-semibold">{post.metadata.author?.title}</span>
  </section>
  {
    post.metadata.cover_image && (
      <Image
        src={post.metadata.cover_image.imgix_url}
        format="webp"
        width={1200}
        height={675}
        aspectRatio={16 / 9}
        quality={50}
        alt={`Cover image for the blog ${post.title}`}
        class={'my-12 rounded-md shadow-lg'}
      />
    )
  }
  <div set:html={post.metadata.content} />
</article>
```

--------------------------------

### Render Dynamic Blog Post Page with Props (Astro/HTML)

Source: https://v6.docs.astro.build/en/guides/cms/contentful

This Astro component utilizes the `getStaticPaths()` function to generate dynamic pages for blog posts. It receives title, formatted content (HTML), and date as props and renders them within a basic HTML structure.

```astro
---
import { contentfulClient } from "../../lib/contentful";
import { documentToHtmlString } from "@contentful/rich-text-html-renderer";
import type { BlogPost } from "../../lib/contentful";


export async function getStaticPaths() {
  const { items } = await contentfulClient.getEntries<BlogPost>({
    content_type: "blogPost",
  });
  const pages = items.map((item) => ({
    params: { slug: item.fields.slug },
    props: {
      title: item.fields.title,
      content: documentToHtmlString(item.fields.content),
      date: new Date(item.fields.date).toLocaleDateString(),
    },
  }));
  return pages;
}


const { content, title, date } = Astro.props;
---
<html lang="en">
  <head>
    <title>{title}</title>
  </head>
  <body>
    <h1>{title}</h1>
    <time>{date}</time>
    <article set:html={content} />
  </body>
</html>

```

--------------------------------

### devImageService Configuration

Source: https://v6.docs.astro.build/en/guides/integrations-guide/vercel

Configure the image service to use in development. This option is available for Serverless and Static deployments and defaults to 'sharp'.

```APIDOC
## `devImageService` Configuration

### Description
Allows you to configure which image service to use in development when `imageService` is enabled. This can be useful if you cannot install Sharp’s dependencies on your development machine, but using another image service like Squoosh would allow you to preview images in your dev environment. Build is unaffected and will always use Vercel’s Image Optimization. It can also be set to any arbitrary value in order to use a custom image service instead of Astro’s built-in ones.

### Method
Configuration within `astro.config.mjs`

### Endpoint
N/A

### Parameters
#### Query Parameters
N/A

#### Request Body
N/A

### Request Example
```javascript
import { defineConfig } from 'astro/config';
import vercel from '@astrojs/vercel';


export default defineConfig({
  // ...
  adapter: vercel({
    imageService: true,
    devImageService: 'sharp',
  }),
});
```

### Response
#### Success Response (200)
N/A

#### Response Example
N/A
```

--------------------------------

### Get Help for a Specific Astro Command (e.g., `dev`) with npm, pnpm, or Yarn

Source: https://v6.docs.astro.build/en/reference/cli-reference

Retrieves a list of all available flags for a specific Astro command, such as `dev`. This allows for detailed customization of command behavior. The `--` separator is necessary for npm to pass flags to the underlying command.

```bash
# get a list of all flags for the `dev` command
npm run dev -- --help
```

```bash
# get a list of all flags for the `dev` command
pnpm dev --help
```

```bash
# get a list of all flags for the `dev` command
yarn dev --help
```

--------------------------------

### Run Cypress Tests from Command Line

Source: https://v6.docs.astro.build/en/guides/testing

These commands execute Cypress tests. `npx cypress run` executes all tests headlessly in the terminal, suitable for CI environments. `npx cypress open` launches the Cypress App, providing a GUI for running and debugging tests interactively.

```bash
npx cypress run
```

```bash
npx cypress open
```

--------------------------------

### Configure Font Fallbacks (JavaScript)

Source: https://v6.docs.astro.build/en/reference/experimental-flags/fonts

Example of setting fallback fonts for a font configuration. This array specifies alternative fonts to use if the primary font is unavailable or loading. An empty array disables fallbacks.

```javascript
fallbacks: ["CustomFont", "serif"]
```

```javascript
fallbacks: []
```

--------------------------------

### Upgrade Astro and Integrations using npm

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v3

Update Astro to the latest version and install the latest versions of Astro integrations like React and Tailwind using npm. This ensures compatibility with Astro v3.x.

```bash
# Upgrade to Astro v3.x
npm install astro@latest

# Example: upgrade React and Tailwind integrations
npm install @astrojs/react@latest @astrojs/tailwind@latest
```

--------------------------------

### Implement Live Loader for CMS Data Fetching (TypeScript)

Source: https://v6.docs.astro.build/en/reference/content-loader-reference

This example demonstrates a live loader in TypeScript that fetches article data from a CMS. It includes type safety for articles and filters, and implements error handling for both collection and entry loading. It relies on a custom `fetchFromCMS` utility.

```typescript
import type { LiveLoader } from 'astro/loaders';
import { fetchFromCMS } from './cms-client.js';


interface Article {
  id: string;
  title: string;
  htmlContent: string;
  author: string;
}


interface EntryFilter {
  id: string;
}


interface CollectionFilter {
  author?: string;
}


export function articleLoader(config: { apiKey: string }): LiveLoader<Article, EntryFilter, CollectionFilter> {
  return {
    name: 'article-loader',
    loadCollection: async ({ filter }) => {
      try {
        const articles = await fetchFromCMS({
          apiKey: config.apiKey,
          type: 'article',
          filter,
        });


        return {
          entries: articles.map((article) => ({
            id: article.id,
            data: article,
          })),
        };
      } catch (error) {
        return {
          error: new Error('Failed to load articles', { cause: error }),
        };
      }
    },
    loadEntry: async ({ filter }) => {
      try {
        // filter will be { id: "some-id" } when called with a string
        const article = await fetchFromCMS({
          apiKey: config.apiKey,
          type: 'article',
          id: filter.id,
        });


        if (!article) {
          return {
            error: new Error('Article not found'),
          };
        }


        return {
          id: article.id,
          data: article,
          rendered: {
            html: article.htmlContent,
          },
        };
      } catch (error) {
        return {
          error: new Error('Failed to load article', { cause: error }),
        };
      }
    },
  };
}
```

--------------------------------

### Define a Live Content Collection with a Custom Loader

Source: https://v6.docs.astro.build/en/reference/modules/astro-content

Illustrates the configuration of a live content collection using `defineLiveCollection`. This example utilizes a custom `storeLoader` to fetch data from a remote API endpoint at runtime, with API key authentication.

```javascript
import { defineLiveCollection } from 'astro:content';
import { storeLoader } from '@example/astro-loader';


const products = defineLiveCollection({
  loader: storeLoader({
    apiKey: process.env.STORE_API_KEY,
    endpoint: 'https://api.example.com/v1',
  }),
});


// Expose your defined collection to Astro
// with the `collections` export
export const collections = { products };
```

--------------------------------

### Heroku Site Deployment and Opening

Source: https://v6.docs.astro.build/en/guides/deploy/heroku

Deploys the site to Heroku by pushing the master branch to the Heroku remote and then opens the deployed site in a browser.

```shell
# publish site
$ git push heroku master


# opens a browser to view the Dashboard version of Heroku CI
$ heroku open
```

--------------------------------

### Fetch All Articles from Drupal JSON:API

Source: https://v6.docs.astro.build/en/guides/cms/drupal

Construct a GET request URL to retrieve a list of all articles from your Drupal site using the JSON:API endpoint. This URL follows the pattern `/jsonapi/node/article`.

```http
GET: [DRUPAL_BASE_URL]/jsonapi/node/article

```

--------------------------------

### Resolve Images with Absolute URL Path in Astro

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

Use absolute URL paths for assets located in the `public/` directory. This is the recommended and simplest method for referencing assets, especially for new Astro users.

```html
<img src="/penguin.png">
```

--------------------------------

### Configure i18n Fallback Strategy in Astro

Source: https://v6.docs.astro.build/en/reference/configuration-reference

Set up a fallback locale strategy for internationalized (i18n) routing in Astro. This example defines fallbacks for 'pt' to 'es' and 'fr' to 'en', with 'es' having no fallback.

```javascript
export default defineConfig({
  i18n: {
    defaultLocale: "en",
    locales: ["en", "fr", "pt-br", "es"],
    fallback: {
      pt: "es",
      fr: "en"
    }
  }
})
```

--------------------------------

### Load Environment Variables with dotenvx in Astro

Source: https://v6.docs.astro.build/en/guides/integrations-guide/node

This command shows how to use `dotenvx` to load environment variables before running an Astro application. It's useful for self-hosting where environment variables need to be explicitly loaded.

```bash
npx @dotenvx/dotenvx run -- node ./dist/server/entry.mjs
```

--------------------------------

### Create Better Auth Client for Vue

Source: https://v6.docs.astro.build/en/guides/authentication

This code snippet shows the setup for a Better Auth client within a Vue.js application. It utilizes the `createAuthClient` function from 'better-auth/vue' and exports the client instance and authentication utilities.

```typescript
import { createAuthClient } from 'better-auth/vue';


export const authClient = createAuthClient();


export const {signIn, signOut } = authClient;

```

--------------------------------

### Configure Cypress for Astro Project

Source: https://v6.docs.astro.build/en/guides/testing

This configuration sets up Cypress for end-to-end testing in an Astro project. It defines the e2e testing options, specifically disabling the support file, which simplifies the initial setup for basic tests.

```javascript
import { defineConfig } from 'cypress';


export default defineConfig({
  e2e: {
    supportFile: false
  }
});
```

--------------------------------

### Fetch Blog Posts in Astro

Source: https://v6.docs.astro.build/en/guides/cms/flotiq

Fetch a list of blog posts from Flotiq within an Astro page component. This code snippet demonstrates how to use the configured Flotiq SDK to retrieve data, preparing it for display.

```astro
---
import { flotiq } from "../lib/flotiq";


const posts = await flotiq.BlogpostAPI.list();
---

```

--------------------------------

### Styling Page-Specific Elements in Astro Layout

Source: https://v6.docs.astro.build/en/tutorial/4-layouts/1

Shows how to move a `<style>` tag from a page's head to its body to style elements specific to that page when using a layout. It also illustrates using `is:global` to apply styles to all elements on the page, including those rendered by the layout.

```astro
<style>
  /* Styles for elements created in this page component */
</style>

<style is:global define:vars={{ skillColor, fontWeight, textCase }}>
  /* Styles affecting all elements on this page */
</style>
```

--------------------------------

### Configure Cosmic API Keys in .env

Source: https://v6.docs.astro.build/en/guides/cms/cosmic

Sets up public environment variables in a .env file at the root of your Astro project. These variables store your Cosmic Bucket Slug and Read Key, which are essential for authenticating API requests.

```env
PUBLIC_COSMIC_BUCKET_SLUG=YOUR_BUCKET_SLUG
PUBLIC_COSMIC_READ_KEY=YOUR_READ_KEY
```

--------------------------------

### Upload File using Cloudinary Node.js SDK in Astro

Source: https://v6.docs.astro.build/en/guides/media/cloudinary

Shows an example of uploading a file using the Cloudinary Node.js SDK within an Astro component. This utilizes the configured Cloudinary instance to interact with Cloudinary's upload API.

```javascript
await cloudinary.uploader.upload('./path/to/file');

```

--------------------------------

### Filter Markdown Files with import.meta.glob() in Astro

Source: https://v6.docs.astro.build/en/guides/imports

Demonstrates a workaround for Vite's import.meta.glob() limitation of only supporting static string literals. This example imports all Markdown files in a directory and then filters them to find a specific post based on its slug.

```astro
---
const { postSlug } = Astro.props;
const pathToMyFeaturedPost = `src/pages/blog/${postSlug}.md`;


const posts = Object.values(import.meta.glob("../pages/blog/*.md", { eager: true }));
const myFeaturedPost = posts.find(post => post.file.includes(pathToMyFeaturedPost));
---


<p>
  Take a look at my favorite post, <a href={myFeaturedPost.url}>{myFeaturedPost.frontmatter.title}</a>!
</p>
```

--------------------------------

### Protect Astro Routes with Middleware

Source: https://v6.docs.astro.build/en/guides/authentication

This example shows how to implement middleware in Astro to protect routes like '/dashboard'. It checks if a user is authenticated using `auth.api.getSession` and redirects them to the home page if they are not logged in and try to access the protected route.

```typescript
import { auth } from "../../../auth"; // import your Better Auth instance
import { defineMiddleware } from "astro:middleware"


export const onRequest = defineMiddleware(async (context, next) => {
  const isAuthed = await auth.api
    .getSession({
      headers: context.request.headers,
    })
  if (context.url.pathname === "/dashboard" && !isAuthed) {
    return context.redirect("/");
  }
  return next();
});

```

--------------------------------

### Constructing URLs using Astro.url and Astro.site

Source: https://v6.docs.astro.build/en/reference/api-reference

Demonstrates how to construct new URLs using the `Astro.url` object and the `Astro.site` configuration. This is useful for creating canonical URLs, social image URLs, or any other URLs relative to the site's domain or the current request.

```astro
---
// Example: Construct a canonical URL using your production domain
const canonicalURL = new URL(Astro.url.pathname, Astro.site);
// Example: Construct a URL for SEO meta tags using your current domain
const socialImageURL = new URL('/images/preview.png', Astro.url);
---
<link rel="canonical" href={canonicalURL} />
<meta property="og:image" content={socialImageURL} />
```

--------------------------------

### Defining a Custom Astro Integration Hook

Source: https://v6.docs.astro.build/en/reference/integrations-reference

Provides an example of how to define a custom integration hook by augmenting the global `Astro.IntegrationHook` interface. This allows for custom event listeners within Astro integrations.

```typescript
declare global {
  namespace Astro {
    export interface IntegrationHook {
      'your:hook': (params: YourHookParameters) => Promise<void>
    }
  }
}
```

--------------------------------

### Configure CSP Style Hashes in Astro

Source: https://v6.docs.astro.build/en/reference/configuration-reference

Adds custom SHA hashes to the 'style-src' directive in the Content Security Policy. Ensure hashes start with 'sha384-', 'sha512-', or 'sha256-'. These are appended to all pages.

```javascript
import { defineConfig } from 'astro/config';


export default defineConfig({
  security: {
    csp: {
      styleDirective: {
        hashes: [
          "sha384-styleHash",
          "sha512-styleHash",
          "sha256-styleHash"
        ]
      }
    }
  }
});
```

--------------------------------

### Render Astro Component to String using renderToString

Source: https://v6.docs.astro.build/en/reference/container-reference

This snippet shows how to use the `renderToString` function to render an Astro component (`Card`) within an Astro container and get the resulting HTML string. It requires importing `experimental_AstroContainer` and the component itself.

```javascript
import { experimental_AstroContainer } from "astro/container";
import Card from "../src/components/Card.astro";


const container = await experimental_AstroContainer.create();
const result = await container.renderToString(Card);
```

--------------------------------

### Generate Blog Post Pages with Static Site Generation in Astro

Source: https://v6.docs.astro.build/en/guides/cms/storyblok

Uses Astro's getStaticPaths to generate dynamic routes for blog posts by fetching slugs from the Storyblok API. Each slug corresponds to a unique blog post page.

```astro
---
import { useStoryblokApi } from '@storyblok/astro'
import StoryblokComponent from '@storyblok/astro/StoryblokComponent.astro'


export async function getStaticPaths() {
  const sbApi = useStoryblokApi();


  const { data } = await sbApi.get("cdn/stories", {
    content_type: "blogPost",
    version: import.meta.env.DEV ? "draft" : "published",
  });


  const stories = Object.values(data.stories);


  return stories.map((story) => {
    return {
      params: { slug: story.slug },
    };
  });
}


const sbApi = useStoryblokApi();
const { slug } = Astro.params;
const { data } = await sbApi.get(`cdn/stories/blog/${slug}`, {
  version: import.meta.env.DEV ? "draft" : "published",
});


const story = data.story;
---


<html lang="en">
  <head>
    <title>Storyblok & Astro</title>
  </head>
  <body>
    <StoryblokComponent blok={story.content} />
  </body>
</html>

```

--------------------------------

### Import Astro DB client

Source: https://v6.docs.astro.build/en/guides/astro-db

This import statement shows how to access the built-in Astro DB client, which provides a type-safe interface for querying your database using Drizzle ORM. No additional setup is required.

```javascript
import { db } from 'astro:db';
```

--------------------------------

### Astro Build Hook for Writing Output Directory Info (JavaScript)

Source: https://v6.docs.astro.build/en/reference/modules/astro-config

An example of a custom Astro integration that uses the `astro:build:done` hook. It imports `outDir` from `astro:config/server` and uses Node.js `fs` and `url` modules to write a `result.json` file within the output directory.

```javascript
import { outDir } from "astro:config/server";
import { writeFileSync } from "node:fs";
import { fileURLToPath } from "node:url";


export default function() {
  return {
    name: "internal-integration",
    hooks: {
      "astro:build:done": () => {
        let file = new URL("result.json", outDir);
        // generate data from some operation
        let data = JSON.stringify([]);
        writeFileSync(fileURLToPath(file), data, "utf-8");
      }
    }
  }
}
```

--------------------------------

### Define Xata Database URL Configuration

Source: https://v6.docs.astro.build/en/guides/backend/xata

Specifies the database URL for the Xata client. This configuration is often part of a JSON object used to initialize the connection to your Xata database.

```json
{
  "databaseUrl": "https://your-database-url"
}
```

--------------------------------

### Add Astro Integration to package.json

Source: https://v6.docs.astro.build/en/reference/integrations-reference

To make your integration discoverable by `astro add`, include the `astro-integration` keyword in your project's `package.json` file. This allows users to install your integration using `astro add <your-package-name>`.

```json
{
  "name": "example",
  "keywords": ["astro-integration"]
}

```

--------------------------------

### Add CNAME File for Custom Domain

Source: https://v6.docs.astro.build/en/guides/deploy/github

Create a CNAME file in the `public/` directory of your Astro project. This file should contain a single line specifying your custom domain, which tells GitHub Pages to serve your site from that domain.

```text
sub.example.com
```

--------------------------------

### Dynamic Content Fetching and Rendering with Astro and DatoCMS

Source: https://v6.docs.astro.build/en/guides/cms/datocms

Fetches modular content from DatoCMS using GraphQL and dynamically renders different components (Image, Text) based on the '_modelApiKey'. Includes API key configuration and response handling.

```astro
---
import Image from '../components/Image.astro';
import Text from '../components/Text.astro';


const response = await fetch('https://graphql.datocms.com/', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    Accept: 'application/json',
    Authorization: `Bearer ${import.meta.env.DATOCMS_API_KEY}`,
  },
  body: JSON.stringify({
    query: `query Homepage {
          home {
            title
            content {
              ... on ImageRecord {
                _modelApiKey
               image{
                url
               }
              }
              ... on TextRecord {
                _modelApiKey
                text(markdown: true)
              }
            }
          }
        }`,
  }),
});


const json = await response.json();
const data = json.data.home;
---


<h1>{data.title}</h1>
{
  data.content.map((item: any) => {
    switch (item._modelApiKey) {
      case 'image':
        return <Image item={item} />;
      case 'text':
        return <Text item={item} />;
      default:
        return null;
    }
  })
}

```

--------------------------------

### Configure includeFiles in Astro Netlify Adapter

Source: https://v6.docs.astro.build/en/guides/integrations-guide/netlify

The includeFiles property allows specifying additional files to be bundled with your function, useful for data, configuration, or template files not automatically detected. Provide an array of file paths relative to the project's root.

```javascript
import { defineConfig } from 'astro/config';
import netlify from '@astrojs/netlify';


export default defineConfig({
  // ...
  adapter: netlify({
    includeFiles: ['./my-data.json'], // relative to `root`
  }),
});

```

--------------------------------

### Add sitemap link to HTML head

Source: https://v6.docs.astro.build/en/guides/integrations-guide/sitemap

Example of how to add a `<link rel="sitemap">` element to your site's `<head>` section to help crawlers discover the sitemap index file.

```html
<head>
  <link rel="sitemap" href="/sitemap-index.xml" />
</head>

```

--------------------------------

### Upgrade Astro and Integrations using Yarn

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v3

Update Astro to the latest version and install the latest versions of Astro integrations like React and Tailwind using Yarn. This ensures compatibility with Astro v3.x.

```bash
# Upgrade to Astro v3.x
yarn add astro@latest

# Example: upgrade React and Tailwind integrations
yarn add @astrojs/react@latest @astrojs/tailwind@latest
```

--------------------------------

### Run Astro Application with Inline Environment Variables

Source: https://v6.docs.astro.build/en/guides/integrations-guide/node

This command demonstrates how to run an Astro application with environment variables set inline. This method is suitable for self-hosting scenarios where direct CLI commands are used.

```bash
DB_HOST=... DB_PASSWORD=... node ./dist/server/entry.mjs
```

--------------------------------

### Create Markdown Blog Post Content in Astro

Source: https://v6.docs.astro.build/en/tutorial/2-pages/2

These snippets provide sample content for Markdown blog posts (`.md` files) in Astro. Each includes YAML frontmatter for metadata like title, author, description, image, publication date, and tags, followed by the post's body content.

```markdown
---
title: My Second Blog Post
author: Astro Learner
description: "After learning some Astro, I couldn't stop!"
image:
    url: "https://docs.astro.build/assets/arc.webp"
    alt: "The Astro logo on a dark background with a purple gradient arc."
pubDate: 2022-07-08
tags: ["astro", "blogging", "learning in public", "successes"]
---
After a successful first week learning Astro, I decided to try some more. I wrote and imported a small component from memory!

```

```markdown
---
title: My Third Blog Post
author: Astro Learner
description: "I had some challenges, but asking in the community really helped!"
image:
    url: "https://docs.astro.build/assets/rays.webp"
    alt: "The Astro logo on a dark background with rainbow rays."
pubDate: 2022-07-15
tags: ["astro", "learning in public", "setbacks", "community"]
---
It wasn't always smooth sailing, but I'm enjoying building with Astro. And, the [Discord community](https://astro.build/chat) is really friendly and helpful!

```

--------------------------------

### Filter Collection Entries by ID (Nested Directories) (Astro)

Source: https://v6.docs.astro.build/en/guides/content-collections

This example illustrates filtering collection entries based on their `id` property, which is useful for targeting specific sub-directories within a collection. It retrieves only entries from the 'en/' directory in the 'docs' collection.

```javascript
// Example: Filter entries by sub-directory in the collection
import { getCollection } from 'astro:content';
const englishDocsEntries = await getCollection('docs', ({ id }) => {
  return id.startsWith('en/');
});
```

--------------------------------

### Display List of Articles on Homepage (Astro)

Source: https://v6.docs.astro.build/en/guides/cms/strapi

Renders a list of blog post titles on the homepage, with each title linking to its respective article page. It fetches articles using `fetchApi` and maps over the `articles` array to create list items. Each list item contains a link to the article's slug-based URL.

```astro
---
import fetchApi from '../lib/strapi';
import type Article from '../interfaces/article';


const articles = await fetchApi<Article[]>({
  endpoint: 'articles?populate=image',
  wrappedByKey: 'data',
});
---


<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Strapi & Astro</title>
  </head>


  <body>
    <main>
      <ul>
        {
          articles.map((article) => (
            <li>
              <a href={`/blog/${article.slug}/`}>
                {article.title}
              </a>
            </li>
          ))
        }
      </ul>
    </main>
  </body>
</html>
```

--------------------------------

### Display Individual Blog Post in Astro

Source: https://v6.docs.astro.build/en/guides/cms/apostrophecms

Astro component to display a single blog post. It uses the `<AposArea>` component to render widgets from the content field and displays the title, author name, and publication date.

```astro
---
import AposArea from '@apostrophecms/apostrophe-astro/components/AposArea.astro';
import dayjs from 'dayjs';


const { page, piece } = Astro.props.aposData;
const { main } = piece;
---


<section class="bp-content">
  <h1>{ piece.title }</h1>
  <h3>Created by: { piece.authorName }
  <h4>
    Released On { dayjs(piece.publicationDate).format('MMMM D, YYYY') }
  </h4>
  <AposArea area={content} />
</section>
```

--------------------------------

### Set Response Status and Headers with Astro Response

Source: https://v6.docs.astro.build/en/reference/api-reference

This example demonstrates how to modify the HTTP response using `Astro.response`. It shows how to set the status code and status text conditionally, and how to add a cookie using the `headers.set()` method. This is useful for controlling the server's response to a client.

```html
---
if (condition) {
  Astro.response.status = 404;
  Astro.response.statusText = 'Not found';
}
---

```

```html
---
Astro.response.headers.set('Set-Cookie', 'a=b; Path=/;');
---

```

--------------------------------

### Send Message from Server to Client (JavaScript)

Source: https://v6.docs.astro.build/en/reference/dev-toolbar-app-reference

Sends a message from the server-side integration to a client-side toolbar app using the `toolbar.send` method within the `astro:server:setup` hook.

```javascript
'astro:server:setup': ({ toolbar }) => {
  toolbar.send('server-message', { message: 'Hello!' });
},
```

--------------------------------

### Initialize NodeApp for SSR in Astro

Source: https://v6.docs.astro.build/en/reference/adapter-reference

Initializes a NodeApp instance for rendering prebuilt pages in a Node.js environment. It accepts an SSR manifest and an optional streaming option, providing server-side rendering capabilities.

```javascript
import { NodeApp } from 'astro/app/node';
import http from 'http';


export function start(manifest) {
  const nodeApp = new NodeApp(manifest);


  addEventListener('fetch', event => {
    event.respondWith(
      nodeApp.render(event.request)
    );
  });
}
```

--------------------------------

### Create Zerops Project and Static Service (YAML)

Source: https://v6.docs.astro.build/en/guides/deploy/zerops

Defines a Zerops project named 'recipe-astro' with a 'static' type service named 'app'. This YAML structure is used for importing or creating projects and services.

```yaml
# see https://docs.zerops.io/references/import for full reference
project:
  name: recipe-astro
services:
  - hostname: app
    type: static

```

--------------------------------

### Use astro:before-preparation and astro:after-preparation for loading indicator

Source: https://v6.docs.astro.build/en/guides/view-transitions

Demonstrates a simpler method for managing a loading indicator using two Astro events. 'astro:before-preparation' adds a 'show' class to a loading element, and 'astro:after-preparation' removes it once content is loaded.

```javascript
<script is:inline>
document.addEventListener("astro:before-preparation", () => {
  document.querySelector("#loading").classList.add("show");
});
document.addEventListener("astro:after-preparation", () => {
  document.querySelector("#loading").classList.remove("show");
});
</script>
```

--------------------------------

### Fetch all posts from Cosmic using Astro SDK

Source: https://v6.docs.astro.build/en/guides/cms/cosmic

Creates an asynchronous function `getAllPosts` in `src/lib/cosmic.js` to fetch metadata for all objects of type 'posts' from your Cosmic bucket. It utilizes the Cosmic JS SDK and environment variables for configuration.

```javascript
import { createBucketClient } from '@cosmicjs/sdk'


const cosmic = createBucketClient({
  bucketSlug: import.meta.env.PUBLIC_COSMIC_BUCKET_SLUG,
  readKey: import.meta.env.PUBLIC_COSMIC_READ_KEY
})


export async function getAllPosts() {
  const data = await cosmic.objects
    .find({
      type: 'posts'
    })
    .props('title,slug,metadata,created_at')
  return data.objects
}
```

--------------------------------

### Configure Build Script for Type Checking

Source: https://v6.docs.astro.build/en/guides/typescript

To prevent code from building if it contains TypeScript errors, modify your `package.json` build script. This example shows how to prepend `astro check` to the existing `astro build` command.

```json
{
  "scripts": {
    "build": "astro build && astro check",
  }
}

```

--------------------------------

### Import Local Markdown Files with Astro Glob

Source: https://v6.docs.astro.build/en/tutorial/5-astro-api/1

This code snippet shows how to import all markdown files from a specific directory using `import.meta.glob`. The `eager: true` option ensures all modules are loaded immediately. This is useful for fetching blog posts or other local content.

```javascript
const myPosts = Object.values(import.meta.glob('./posts/*.md', { eager: true }));
```

--------------------------------

### Update Astro Preview Script for Deno

Source: https://v6.docs.astro.build/en/guides/deploy/deno

Modifies the `preview` script in `package.json` to use Deno for running the production build locally. This allows testing the on-demand rendered site with Deno.

```json
{
  // ...
  "scripts": {
    "dev": "astro dev",
    "start": "astro dev",
    "build": "astro build",
    "preview": "astro preview"
    "preview": "deno run --allow-net --allow-read --allow-env ./dist/server/entry.mjs"
  }
}
```

--------------------------------

### Accessing Integration Data with refreshContextData in JavaScript

Source: https://v6.docs.astro.build/en/reference/content-loader-reference

The `refreshContextData` object provides optional extra data when a loader is triggered by an integration. This example shows how to check for and process webhook data passed through `refreshContextData`.

```javascript
import type { Loader } from "astro/loaders";
import { processWebhook } from "./lib/webhooks";


export function myLoader(options: { url: string }) {
  return {
    name: "my-loader",
    load: async ({ refreshContextData, store, logger }) => {
      if(refreshContextData?.webhookBody) {
        logger.info("Webhook triggered with body");
        processWebhook(store, refreshContextData.webhookBody);
      }
      // ...
    },
  } satisfies Loader;
}
```

--------------------------------

### Create Blog Piece and Page Type using Apostrophe CLI (Shell)

Source: https://v6.docs.astro.build/en/guides/cms/apostrophecms

This command uses the ApostropheCMS CLI to generate a new 'blog' piece type and its corresponding piece page type. This is the initial step for creating a blog functionality within an ApostropheCMS project.

```bash
apos add piece blog --page

```

--------------------------------

### Load Vercel Environment Variables Locally

Source: https://v6.docs.astro.build/en/guides/integrations-guide/vercel

Use the Vercel CLI command `vercel env pull .env.local` to download your project's environment variables. This creates a `.env.local` file, essential for connecting to your Redis database during local development.

```bash
vercel env pull .env.local
```

--------------------------------

### Define Contentful Environment Variables Interface in Astro

Source: https://v6.docs.astro.build/en/guides/cms/contentful

Enhance IntelliSense for Contentful environment variables in Astro by defining an ImportMetaEnv interface in env.d.ts. This provides type safety and autocompletion for your credentials.

```typescript
interface ImportMetaEnv {
  readonly CONTENTFUL_SPACE_ID: string;
  readonly CONTENTFUL_DELIVERY_TOKEN: string;
  readonly CONTENTFUL_PREVIEW_TOKEN: string;
}
```

--------------------------------

### Declare Astro Adapter Feature Support

Source: https://v6.docs.astro.build/en/reference/adapter-reference

An example of how an Astro adapter can declare its support for specific Astro features, such as the Sharp-powered built-in image service. This configuration allows Astro to perform validation and emit contextual information.

```javascript
export default function createIntegration() {
  return {
    name: '@example/my-adapter',
    hooks: {
      'astro:config:done': ({ setAdapter }) => {
        setAdapter({
          name: '@example/my-adapter',
          serverEntrypoint: '@example/my-adapter/server.js',
          supportedAstroFeatures: {
            sharpImageService: 'experimental'
          }
        });
      },
    },
  };
}
```

--------------------------------

### Astro Configuration for Storyblok Integration

Source: https://v6.docs.astro.build/en/guides/cms/storyblok

Configures the Storyblok integration for Astro, including the access token and mapping of Storyblok component names to Astro component paths. Supports region selection.

```javascript
import { defineConfig } from 'astro/config';
import { storyblok } from '@storyblok/astro';
import { loadEnv } from 'vite';


const env = loadEnv("", process.cwd(), 'STORYBLOK');


export default defineConfig({
  integrations: [
    storyblok({
      accessToken: env.STORYBLOK_TOKEN,
      components: {
        blogPost: 'storyblok/BlogPost',
        blogPostList: 'storyblok/BlogPostList',
        page: 'storyblok/Page',
      },
      apiOptions: {
        region: 'us',
      },
    })
  ],
});

```

--------------------------------

### Remove Usage of Internal Session 'test' Driver

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v6

This code example shows how to remove the usage of the internal session 'test' driver from the Astro configuration. This driver was previously exposed in config types but is no longer supported in Astro 6.0.

```typescript
import { defineConfig } from 'astro/config'
import { createMockStorage } from './utils'


export default defineConfig({
  session: {
    driver: 'test',
    options: {
      mockStorage: createMockStorage()
    }
  }
})
```

--------------------------------

### Dynamic Route Page Generation with Strapi (Astro)

Source: https://v6.docs.astro.build/en/guides/cms/strapi

Generates a dynamic blog post page by fetching article data from Strapi based on the URL slug. It handles data fetching, error redirection to a 404 page, and renders the article's title, image, content (as plain text, markdown, and HTML). Dependencies include a `fetchApi` utility and an `Article` interface.

```astro
---
import fetchApi from '../../../lib/strapi';
import type Article from '../../../interfaces/article';


const { slug } = Astro.params;


let article: Article;


try {
  article = await fetchApi<Article>({
    endpoint: 'articles',
    wrappedByKey: 'data',
    wrappedByList: true,
    query: {
      'filters[slug][$eq]': slug || '',
    },
  });
} catch (error) {
  return Astro.redirect('/404');
}
---


<!DOCTYPE html>
<html lang="en">
  <head>
    <title>{article.title}</title>
  </head>


  <body>
    <main>
      <img src={import.meta.env.STRAPI_URL + article.image.data.url} />


      <h1>{article.title}</h1>


      <!-- Render plain text -->
      <p>{article.content}</p>
      <!-- Render markdown -->
      <MyMarkdownComponent>
        {article.content}
      </MyMarkdownComponent>
      <!-- Render html -->
      <Fragment set:html={article.content} />
    </main>
  </body>
</html>

```

--------------------------------

### Map Astro Components to ApostropheCMS Page Types

Source: https://v6.docs.astro.build/en/guides/cms/apostrophecms

Configuration file to map Astro components to specific ApostropheCMS page types. This ensures that the correct Astro template is rendered for different page types, including the blog index and show pages.

```javascript
import HomePage from './HomePage.astro';
import BlogIndexPage from './BlogIndexPage.astro';
import BlogShowPage from './BlogShowPage.astro';


const templateComponents = {
  '@apostrophecms/home-page': HomePage,
  '@apostrophecms/blog-page:index': BlogIndexPage,
  '@apostrophecms/blog-page:show': BlogShowPage
};


export default templateComponents;
```

--------------------------------

### Explicit Type Imports and Exports

Source: https://v6.docs.astro.build/en/guides/typescript

This example demonstrates the correct syntax for explicit type imports and exports in TypeScript. Using `import type` prevents Astro's bundler from incorrectly processing types as JavaScript, ensuring type safety.

```typescript
import { SomeType } from "./script";
import type { SomeType } from "./script";
```

--------------------------------

### Add Dev Toolbar App Integration in Astro

Source: https://v6.docs.astro.build/en/reference/dev-toolbar-app-reference

This JavaScript code demonstrates how to set up an Astro integration to add a custom application to the Astro Dev Toolbar. It utilizes the `addDevToolbarApp` function within the `astro:config:setup` hook, specifying the app's ID, name, icon, and entrypoint. The `entrypoint` can be a string path or a URL object.

```javascript
/**
 * @type {() => import('astro').AstroIntegration}
 */
export default () => ({
  name: "my-integration",
  hooks: {
    "astro:config:setup": ({ addDevToolbarApp }) => {
      addDevToolbarApp({
        id: "my-app",
        name: "My App",
        icon: "<svg>...</svg>",
        entrypoint: "./my-app.js",
      });
    },
  },
});
```

```javascript
/**
 * @type {() => import('astro').AstroIntegration}
 */
export default () => ({
  name: "my-integration",
  hooks: {
    "astro:config:setup": ({ addDevToolbarApp }) => {
      addDevToolbarApp({
        id: "my-app",
        name: "My App",
        icon: "<svg>...</svg>",
        entrypoint: new URL("./my-app.js", import.meta.url),
      });
    },
  },
});
```

--------------------------------

### Run Astro Website Docker Container Locally

Source: https://v6.docs.astro.build/en/recipes/docker

Runs the previously built Docker image as a local container. It maps a local port to a port exposed by the container, allowing access to the website via localhost. Ensure to replace placeholders with actual port numbers and image name.

```bash
docker run -p <local-port>:<container-port> <your-astro-image-name>
```

--------------------------------

### Fetch Blog Post Entries for Static Paths (Astro/TypeScript)

Source: https://v6.docs.astro.build/en/guides/cms/contentful

This snippet demonstrates fetching blog post entries from Contentful within the `getStaticPaths()` function in an Astro page. It imports necessary modules and specifies the content type to retrieve.

```astro
---
import { contentfulClient } from "../../lib/contentful";
import type { BlogPost } from "../../lib/contentful";


export async function getStaticPaths() {
  const entries = await contentfulClient.getEntries<BlogPost>({
    content_type: "blogPost",
  });
}
---

```

--------------------------------

### Return Client IP Address in Astro API

Source: https://v6.docs.astro.build/en/reference/api-reference

This example demonstrates an Astro API route that returns the client's IP address as a string. It imports `APIContext` and uses destructuring to access `clientAddress` from the context. The `prerender = false` directive is essential for on-demand rendering.

```javascript
export const prerender = false; // Not needed in 'server' mode
import type { APIContext } from 'astro';


export function GET({ clientAddress }: APIContext) {
  return new Response(`Your IP address is: ${clientAddress}`);
}
```

--------------------------------

### Register New User Endpoint (Astro/TypeScript)

Source: https://v6.docs.astro.build/en/guides/backend/supabase

This endpoint handles new user registration. It accepts POST requests with email and password, then uses the Supabase SDK to create a new user. Ensure `export const prerender = false;` if using `static` rendering mode.

```typescript
// With `output: 'static'` configured:
// export const prerender = false;
import type { APIRoute } from "astro";
import { supabase } from "../../../lib/supabase";


export const POST: APIRoute = async ({ request, redirect }) => {
  const formData = await request.formData();
  const email = formData.get("email")?.toString();
  const password = formData.get("password")?.toString();


  if (!email || !password) {
    return new Response("Email and password are required", { status: 400 });
  }


  const { error } = await supabase.auth.signUp({
    email,
    password,
  });


  if (error) {
    return new Response(error.message, { status: 500 });
  }


  return redirect("/signin");
};

```

--------------------------------

### Astro Firebase Sign-out Endpoint

Source: https://v6.docs.astro.build/en/guides/backend/firebase

Implements the GET /api/auth/signout endpoint to log out a user by deleting the session cookie. This is a simple endpoint that redirects the user after clearing the cookie.

```typescript
import type { APIRoute } from "astro";


export const GET: APIRoute = async ({ redirect, cookies }) => {
  cookies.delete("__session", {
    path: "/",
  });
  return redirect("/signin");
};

```

--------------------------------

### Custom 404 Not Found Page (HTML)

Source: https://v6.docs.astro.build/en/guides/cms/strapi

A simple HTML page to display when a requested resource is not found. It includes a title, a message indicating the page does not exist, and an image of a 404 cat. This page is used as a fallback when dynamic content fetching fails.

```html
<html lang="en">
  <head>
    <title>Not found</title>
  </head>
  <body>
    <p>Sorry, this page does not exist.</p>
    <img src="https://http.cat/404" />
  </body>
</html>

```

--------------------------------

### Access a Specific Live Entry in Astro

Source: https://v6.docs.astro.build/en/reference/modules/astro-content

Provides an example of fetching a single live entry from a collection named 'products' using `getLiveEntry` based on a dynamic parameter (Astro.params.id). This is common for detail pages.

```typescript
---
import { getLiveEntry } from 'astro:content';


const { entry } = await getLiveEntry('products', Astro.params.id);
---

```

--------------------------------

### Configure Astro Static Site Build (npm)

Source: https://v6.docs.astro.build/en/guides/deploy/zerops

Specifies the build configuration for an Astro static site using npm. It sets the base Node.js version, build commands, and files to deploy.

```yaml
# see https://docs.zerops.io/zerops-yml/specification for full reference
zerops:
  - setup: app
    build:
      base: nodejs@20
      buildCommands:
        - npm i
        - npm build
      deployFiles:
        - dist/~ 
    run:
      base: static

```

--------------------------------

### Astro Registration Form

Source: https://v6.docs.astro.build/en/guides/backend/supabase

Creates a user registration form that accepts email and password. It submits the data via a POST request to the /api/auth/register endpoint. This page requires the Layout component for structure.

```astro
---
import Layout from "../layouts/Layout.astro";
---


<Layout title="Register">
  <h1>Register</h1>
  <p>Already have an account? <a href="/signin">Sign in</a></p>
  <form action="/api/auth/register" method="post">
    <label for="email">Email</label>
    <input type="email" name="email" id="email" />
    <label for="password">Password</label>
    <input type="password" name="password" id="password" />
    <button type="submit">Register</button>
  </form>
</Layout>
```

--------------------------------

### Gate Astro Actions from Middleware

Source: https://v6.docs.astro.build/en/guides/actions

This example shows how to gate access to all Astro actions from middleware using `getActionContext`. It checks for a valid session token for client-side RPC calls and returns a 'Forbidden' response if the token is missing. This provides a preliminary security layer before actions are invoked.

```typescript
import { defineMiddleware } from 'astro:middleware';
import { getActionContext } from 'astro:actions';


export const onRequest = defineMiddleware(async (context, next) => {
  const { action } = getActionContext(context);
  // Check if the action was called from a client-side function
  if (action?.calledFrom === 'rpc') {
    // If so, check for a user session token
    if (!context.cookies.has('user-session')) {
      return new Response('Forbidden', { status: 403 });
    }
  }


  context.cookies.set('user-session', /* session token */);
  return next();
});
```

--------------------------------

### Generate Static Article Pages with getStaticPaths (Astro)

Source: https://v6.docs.astro.build/en/guides/cms/strapi

Defines `getStaticPaths` for Astro's static site generation (SSG). This function fetches all articles from the Strapi API and returns an array of objects, each containing `params` with the article's `slug` and `props` with the article data. This enables dynamic routing for individual blog posts.

```astro
---
import fetchApi from '../../lib/strapi';
import type Article from '../../interfaces/article';


export async function getStaticPaths() {
  const articles = await fetchApi<Article[]>({
    endpoint: 'articles',
    wrappedByKey: 'data',
  });


  return articles.map((article) => ({
    params: { slug: article.slug },
    props: article,
  }));
}
type Props = Article;


const article = Astro.props;
---
```

--------------------------------

### Using Node.js Buffer Module in Astro

Source: https://v6.docs.astro.build/en/guides/integrations-guide/cloudflare

Demonstrates importing and using the Node.js `Buffer` module within an Astro server-side context when Node.js compatibility is enabled in Cloudflare Workers. This requires the `nodejs_compat` flag to be set in the Wrangler configuration.

```javascript
export const prerender = false; // Not needed in 'server' mode
import { Buffer } from 'node:buffer';

```

--------------------------------

### Set Environment Variables for Node.js Deployment with npm

Source: https://v6.docs.astro.build/en/guides/deploy/clever-cloud

Configures the build environment for a Node.js Astro application using npm. It specifies npm as the build tool and sets a pre-build hook to install dependencies, disable Astro telemetry, and build the project.

```bash
CC_NODE_BUILD_TOOL="npm"
CC_PRE_BUILD_HOOK="npm install && npm run astro telemetry disable && npm run build"
```

--------------------------------

### Run Astro Node Adapter in Standalone Mode

Source: https://v6.docs.astro.build/en/guides/integrations-guide/node

This snippet demonstrates how to run the Astro Node adapter in standalone mode. The server entrypoint `./dist/server/entry.mjs` is executed directly using Node.js. In this mode, the server handles file serving, page routing, and API routes.

```bash
node ./dist/server/entry.mjs

```

--------------------------------

### Add remark and rehype plugins to Astro

Source: https://v6.docs.astro.build/en/guides/markdown-content

This example demonstrates how to add `remark-toc` and `rehype-accessible-emojis` plugins to your Astro project's Markdown configuration. These plugins enable features like automatic table of contents generation and accessible emoji labels.

```javascript
import { defineConfig } from 'astro/config';
import remarkToc from 'remark-toc';
import { rehypeAccessibleEmojis } from 'rehype-accessible-emojis';


export default defineConfig({
  markdown: {
    remarkPlugins: [ [remarkToc, { heading: 'toc', maxDepth: 3 } ] ],
    rehypePlugins: [rehypeAccessibleEmojis],
  },
});
```

--------------------------------

### Storyblok Page Component in Astro

Source: https://v6.docs.astro.build/en/guides/cms/storyblok

A recursive component to render Bloks within the 'body' property of a 'page' Blok. Adds storyblokEditable attributes for in-editor editing.

```astro
---
import { storyblokEditable } from '@storyblok/astro'
import StoryblokComponent from "@storyblok/astro/StoryblokComponent.astro";
const { blok } = Astro.props
---


<main {...storyblokEditable(blok)}>
  {
    blok.body?.map((blok) => {
      return <StoryblokComponent blok={blok} />
    })
  }
</main>

```

--------------------------------

### Import Local JavaScript/TypeScript Files in Astro

Source: https://v6.docs.astro.build/en/guides/client-side-scripts

This example shows how to include local JavaScript or TypeScript files within your Astro project using the `src` attribute of a <script> tag. Astro will process these scripts according to its default rules, including bundling and TypeScript support. The paths are relative to the component file.

```html
<!-- relative path to script at `src/scripts/local.js` -->
<script src="../scripts/local.js"></script>


<!-- also works for local TypeScript files -->
<script src="./script-with-types.ts"></script>
```

--------------------------------

### Render LastUpdated Component for Each Post in Astro

Source: https://v6.docs.astro.build/en/tutorial/5-astro-api/1

This example demonstrates mapping over the `myPosts` array to render a `LastUpdated` component for each blog post. It passes the `pubDate` from the post's frontmatter to the component, allowing dynamic display of update dates.

```javascript
myPosts.map((post) => <LastUpdated date={post.frontmatter.pubDate} />)
```

--------------------------------

### Implement Session Driver using Unstorage Redis Driver

Source: https://v6.docs.astro.build/en/reference/session-driver-reference

Implements an Astro session driver by directly using the Unstorage Redis driver. This example shows how to import the Unstorage driver and use it to fulfill the SessionDriver interface, merging provided configuration with custom TLS settings.

```typescript
import type { SessionDriver } from 'astro'
import redisDriver from "unstorage/drivers/redis";


export default function(config): SessionDriver {
    return redisDriver({
        ...config,
        tls: true
    })
}
```

--------------------------------

### Enable Client Prerendering in Astro Config

Source: https://v6.docs.astro.build/en/reference/experimental-flags/client-prerender

This configuration snippet demonstrates how to enable client-side prerendering and configure prefetching options within the `astro.config.mjs` file. It sets `prefetch.prefetchAll` to true, `prefetch.defaultStrategy` to 'viewport', and enables `experimental.clientPrerender`.

```javascript
{
  prefetch: {
    prefetchAll: true,
    defaultStrategy: 'viewport',
  },
  experimental: {
    clientPrerender: true,
  },
}
```

--------------------------------

### Set Up Contentful Environment Variables in Astro

Source: https://v6.docs.astro.build/en/guides/cms/contentful

Configure Contentful credentials in an Astro project by creating an .env file. These variables store your Contentful space ID and access tokens for both delivery and preview environments.

```env
CONTENTFUL_SPACE_ID=YOUR_SPACE_ID
CONTENTFUL_DELIVERY_TOKEN=YOUR_DELIVERY_TOKEN
CONTENTFUL_PREVIEW_TOKEN=YOUR_PREVIEW_TOKEN
```

--------------------------------

### Update Gatsby Imports to Astro Relative Paths

Source: https://v6.docs.astro.build/en/guides/migrate-to-astro/from-gatsby

File imports in Astro require explicit relative paths, including the file extension. This example demonstrates importing an Astro component using a relative path.

```astro
---
import Card from "../../components/Card.astro";
---
<Card />
```

--------------------------------

### Fetch and Display Page Data in Astro

Source: https://v6.docs.astro.build/en/guides/cms/buttercms

Retrieves a specific page's data from ButterCMS and displays its fields like SEO title, headline, and hero image within an Astro component.

```astro
---
import { butterClient } from "../lib/buttercms";
const response = await butterClient.page.retrieve("*", "simple-page");
const pageData = response.data.data;


interface Fields {
  seo_title: string,
  headline: string,
  hero_image: string,
}


const fields = pageData.fields as Fields;
---
<html>
  <title>{fields.seo_title}</title>
  <body>
    <h1>{fields.headline}</h1>
    <img src={fields.hero_image} />
  </body>
</html>
```

--------------------------------

### Dynamically Display Blog Posts with import.meta.glob() in Astro

Source: https://v6.docs.astro.build/en/tutorial/5-astro-api/1

This code snippet demonstrates how to use `import.meta.glob()` to get all Markdown files from a directory and display them as a list on an Astro blog page. It maps over the imported posts to create list items with links to each post.

```astro
---
import BaseLayout from '../layouts/BaseLayout.astro'
const allPosts = Object.values(import.meta.glob('./posts/*.md', { eager: true }));
const pageTitle = "My Astro Learning Blog";
---
<BaseLayout pageTitle={pageTitle}>
  <p>This is where I will post about my journey learning Astro.</p>
  <ul>
    <li><a href="/posts/post-1/">Post 1</a></li>
    <li><a href="/posts/post-2/">Post 2</a></li>
    <li><a href="/posts/post-3/">Post 3</a></li>
  </ul>
</BaseLayout>
```

```astro
---
import BaseLayout from '../layouts/BaseLayout.astro'
const allPosts = Object.values(import.meta.glob('./posts/*.md', { eager: true }));
const pageTitle = "My Astro Learning Blog";
---
<BaseLayout pageTitle={pageTitle}>
  <p>This is where I will post about my journey learning Astro.</p>
  <ul>
    <li><a href="/posts/post-1/">Post 1</a></li>
    <li><a href="/posts/post-2/">Post 2</a></li>
    <li><a href="/posts/post-3/">Post 3</a></li>


    {allPosts.map((post: any) => <li><a href={post.url}>{post.frontmatter.title}</a></li>)}
  </ul>
</BaseLayout>
```

--------------------------------

### GitHub Actions Deployment for On-Demand Astro Sites

Source: https://v6.docs.astro.build/en/guides/deploy/deno

This GitHub Actions workflow deploys an on-demand Astro site to Deno Deploy. It follows similar steps to the static deployment but specifies a different entry point for the on-demand server. Replace 'my-deno-project' with your Deno Deploy project name.

```yaml
name: Deploy
on: [push]

jobs:
  deploy:
    name: Deploy
    runs-on: ubuntu-latest
    permissions:
      id-token: write # Needed for auth with Deno Deploy
      contents: read # Needed to clone the repository

    steps:
      - name: Clone repository
        uses: actions/checkout@v4

      # Not using npm? Change `npm ci` to `yarn install` or `pnpm i`
      - name: Install dependencies
        run: npm ci

      # Not using npm? Change `npm run build` to `yarn build` or `pnpm run build`
      - name: Build Astro
        run: npm run build

      - name: Upload to Deno Deploy
        uses: denoland/deployctl@v1
        with:
          project: my-deno-project # TODO: replace with Deno Deploy project name
          entrypoint: dist/server/entry.mjs
```

--------------------------------

### Create Custom Rehype Plugin for Heading IDs (Astro)

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v6

Provides a custom rehype plugin (`rehypeSlug`) to generate heading IDs similar to Astro v5, stripping trailing hyphens for backward compatibility. It requires installing `github-slugger`, `hast-util-heading-rank`, `unist-util-visit`, and `hast-util-to-string`.

```bash
npm i github-slugger hast-util-heading-rank unist-util-visit hast-util-to-string
```

```bash
pnpm add github-slugger hast-util-heading-rank unist-util-visit hast-util-to-string
```

```bash
yarn add github-slugger hast-util-heading-rank unist-util-visit hast-util-to-string
```

```javascript
import GithubSlugger from 'github-slugger';
import { headingRank } from 'hast-util-heading-rank';
import { visit } from 'unist-util-visit';
import { toString } from 'hast-util-to-string';


const slugs = new GithubSlugger();


export function rehypeSlug() {
  /**
   * @param {import('hast').Root} tree
   */
  return (tree) => {
    slugs.reset();
    visit(tree, 'element', (node) => {
      if (headingRank(node) && !node.properties.id) {
        let slug = slugs.slug(toString(node));
        // Strip trailing hyphens like in Astro v5 and below:
        if (slug.endsWith('-')) slug = slug.slice(0, -1);
        node.properties.id = slug;
      }
    });
  };
}
```

```javascript
import { defineConfig } from 'astro/config';
import { rehypeSlug } from './plugins/rehype-slug';


export default defineConfig({
  markdown: {
    rehypePlugins: [rehypeSlug],
  },
});
```

--------------------------------

### Astro Page with React Component and ClientRouter

Source: https://v6.docs.astro.build/en/guides/view-transitions

Demonstrates how to integrate a React component into an Astro page that uses `<ClientRouter />` for client-side routing. The `client:load` directive ensures the React component is hydrated and interactive on the client side.

```html
---
import Form from "../components/Form.jsx";
import { ClientRouter } from "astro:transitions";
---
<html>
  <head>
    <ClientRouter />
  </head>
  <body>
    <Form client:load />
  </body>
</html>

```

--------------------------------

### Configure Zephyr Integration in astro.config.mjs

Source: https://v6.docs.astro.build/en/guides/deploy/zephyr

Adds the Zephyr integration to your Astro project's configuration file. This step is part of the manual installation process and enables Zephyr's features for your site.

```javascript
import { defineConfig } from 'astro/config';
import { withZephyr } from 'zephyr-astro-integration';


export default defineConfig({
  integrations: [
    withZephyr(),
  ],
});
```

--------------------------------

### Markdown Frontmatter Layout Property in Astro

Source: https://v6.docs.astro.build/en/guides/markdown-content

This example shows how to use the `layout` frontmatter property in an individual Markdown page to apply an Astro component as a layout. The layout component can access Markdown frontmatter properties via `Astro.props.frontmatter`.

```markdown
---
layout: ../../layouts/BlogPostLayout.astro
title: Astro in brief
author: Himanshu
description: Find out what makes Astro awesome!
---
This is a post written in Markdown.

```

--------------------------------

### Fetch Blog Posts from Contentful (Astro/TypeScript)

Source: https://v6.docs.astro.build/en/guides/cms/contentful

Fetches all blog post entries from Contentful using the `contentfulClient` and types the response using the `BlogPost` interface. This is the initial step for displaying blog posts on an Astro page.

```astro
---
import { contentfulClient } from "../lib/contentful";
import type { BlogPost } from "../lib/contentful";


const entries = await contentfulClient.getEntries<BlogPost>({
  content_type: "blogPost",
});
---

```

--------------------------------

### Optimized Multi-stage Dockerfile for Astro SSR

Source: https://v6.docs.astro.build/en/recipes/docker

This Dockerfile uses multi-stage builds to optimize the Astro SSR build process. It separates dependency installation from source code copying, allowing Docker to cache layers more effectively and reduce build times when only source code changes.

```Dockerfile
FROM node:lts AS base
WORKDIR /app


# By copying only the package.json and package-lock.json here, we ensure that the following `-deps` steps are independent of the source code.
# Therefore, the `-deps` steps will be skipped if only the source code changes.
COPY package.json package-lock.json ./

FROM base AS prod-deps
RUN npm install --omit=dev

FROM base AS build-deps
RUN npm install

FROM build-deps AS build
COPY . .
RUN npm run build

FROM base AS runtime
COPY --from=prod-deps /app/node_modules ./node_modules
COPY --from=build /app/dist ./dist


ENV HOST=0.0.0.0
ENV PORT=4321
EXPOSE 4321
CMD ["node", "./dist/server/entry.mjs"]
```

--------------------------------

### Access and Process Pages Data in Astro Integration

Source: https://v6.docs.astro.build/en/reference/integrations-reference

Provides a Map of pages and their build data, enabling actions based on route criteria during the build setup. Useful for conditional logic or modifications per page.

```javascript
export default {
  name: 'my-integration',
  hooks: {
    'astro:build:setup': ({ pages }) => {
      pages.forEach((data) => {
        if (data.route.pattern.test("/blog")) {
          console.log(data.route.type);
        }
      });
    },
  }
}
```

--------------------------------

### Add Remark Plugins for Markdown Processing in Astro

Source: https://v6.docs.astro.build/en/reference/configuration-reference

Pass remark plugins to Astro to customize Markdown processing. Plugins can be imported directly or specified by name. Example shows adding 'remark-toc'. Requires remark plugins.

```javascript
import remarkToc from 'remark-toc';
{
  markdown: {
    remarkPlugins: [ [remarkToc, { heading: "contents"} ] ]
  }
}

```

--------------------------------

### Astro GitHub Actions Workflow for Deployment

Source: https://v6.docs.astro.build/en/guides/deploy/github

This YAML file configures a GitHub Actions workflow to automatically deploy an Astro site to GitHub Pages on every push to the main branch. It includes steps for checking out the repository, installing dependencies, building the Astro site, and deploying it to GitHub Pages. Permissions are set for content read/write and page deployment.

```yaml
name: Deploy to GitHub Pages

on:
  # Trigger the workflow every time you push to the `main` branch
  # Using a different branch name? Replace `main` with your branch’s name
  push:
    branches: [ main ]
  # Allows you to run this workflow manually from the Actions tab on GitHub.
  workflow_dispatch:

# Allow this job to clone the repo and create a page deployment
permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout your repository using git
        uses: actions/checkout@v5
      - name: Install, build, and upload your site
        uses: withastro/action@v5
        # with:
          # path: . # The root location of your Astro project inside the repository. (optional)
          # node-version: 24 # The specific version of Node that should be used to build your site. Defaults to 22. (optional)
          # package-manager: pnpm@latest # The Node package manager that should be used to install dependencies and build your site. Automatically detected based on your lockfile. (optional)
          # build-cmd: pnpm run build # The command to run to build your site. Runs the package build script/task by default. (optional)
        # env:
          # PUBLIC_POKEAPI: 'https://pokeapi.co/api/v2' # Use single quotation marks for the variable value. (optional)


  deploy:
    needs: build
    runs-on: ubuntu-latest
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4

```

--------------------------------

### Configure remote DB connection URL with options

Source: https://v6.docs.astro.build/en/guides/astro-db

Example of configuring the `ASTRO_DB_REMOTE_URL` environment variable to use a local encrypted file as an embedded replica of a remote libSQL server. This includes encryption, sync interval, and sync URL parameters.

```env
ASTRO_DB_REMOTE_URL=file://local-copy.db?encryptionKey=your-encryption-key&syncInterval=60&syncUrl=libsql%3A%2F%2Fyour.server.io
ASTRO_DB_APP_TOKEN=token-to-your-remote-url
```

--------------------------------

### Inject Types into Astro Project

Source: https://v6.docs.astro.build/en/reference/integrations-reference

This example shows how to use the `injectTypes` function provided by the `astro:config:done` hook to add a new TypeScript declaration file to the user's project. It logs the URL of the injected file.

```javascript
const path = injectTypes({
  filename: "types.d.ts",
  content: "declare module 'virtual:integration' {}"
})
console.log(path) // URL
```

--------------------------------

### Astro Script Processing: Bundling and TypeScript

Source: https://v6.docs.astro.build/en/guides/client-side-scripts

This example shows a basic <script> tag that Astro will process. By default, Astro enables TypeScript support, bundles imports (local or npm), processes scripts as type modules, deduplicates scripts when components are reused, and inlines small scripts.

```javascript
// Processed! Bundled! TypeScript!
// Importing local scripts and from npm packages works.
```

--------------------------------

### Conditional Rewrite in Endpoint Files

Source: https://v6.docs.astro.build/en/guides/routing

Applies a rewrite within an endpoint file using `context.rewrite()`. This example shows redirecting to the root path if a specific condition (`context.locals.allowed`) is not met. It allows for dynamic routing logic in API endpoints.

```javascript
export function GET(context) {
  if (!context.locals.allowed) {
    return context.rewrite("/");
  }
}
```

--------------------------------

### Astro Nested Pagination getStaticPaths

Source: https://v6.docs.astro.build/en/guides/routing

Implements nested pagination in Astro by returning an array of `paginate()` results from `getStaticPaths()`. This example groups posts by tag and ensures Astro correctly associates paginated results with their respective `tag` parameter using `{ params: { tag } }`.

```astro
---
export function getStaticPaths({ paginate }) {
  const allTags = ["red", "blue", "green"];
  const allPosts = Object.values(import.meta.glob("../pages/post/*.md", { eager: true }));
  // For every tag, return a `paginate()` result.
  // Make sure that you pass `{ params: { tag }}` to `paginate()`
  // so that Astro knows which tag grouping the result is for.
  return allTags.flatMap((tag) => {
    const filteredPosts = allPosts.filter((post) => post.frontmatter.tag === tag);
    return paginate(filteredPosts, {
      params: { tag },
      pageSize: 10
    });
  });
}


const { page } = Astro.props;
const params = Astro.params;

---

```

--------------------------------

### Organizing Actions

Source: https://v6.docs.astro.build/en/guides/actions

Illustrates how to organize multiple actions, including nesting them within objects.

```APIDOC
## Organizing Actions

### Description
Actions must be exported from a `server` object in `src/actions/index.ts`. Related actions can be grouped into nested objects for better organization.

### Example Structure

`src/actions/user.ts`:
```typescript
import { defineAction } from 'astro:actions';

export const user = {
  getUser: defineAction({
    // ... definition for getUser
  }),
  createUser: defineAction({
    // ... definition for createUser
  }),
};
```

`src/actions/index.ts`:
```typescript
import { defineAction } from 'astro:actions';
import { user } from './user';

export const server = {
  myAction: defineAction({
    // ... definition for myAction
  }),
  user: user, // Nesting the user actions
};
```

### Calling Organized Actions
- `actions.myAction()`
- `actions.user.getUser()`
- `actions.user.createUser()`
```

--------------------------------

### Type Custom Image Service Props in Astro

Source: https://v6.docs.astro.build/en/reference/image-service-reference

This example demonstrates how to extend Astro's `Astro.CustomImageProps` interface to add types for custom props supported by an image service. This provides autocomplete and type safety for users.

```typescript
declare namespace Astro {
  interface CustomImageProps {
    /** Apply a Gaussian blur with this radius to the image. */
    blur?: number;
  }
}
```

--------------------------------

### Customize Vite Server in Astro Integration

Source: https://v6.docs.astro.build/en/reference/integrations-reference

This code illustrates how to modify the Vite development server within an Astro integration using the `astro:server:setup` hook. It demonstrates adding custom middleware to the server's request handling pipeline.

```javascript
export default {
  name: 'partytown',
  hooks: {
    'astro:server:setup': ({ server }) => {
      server.middlewares.use(
        function middleware(req, res, next) {
          // handle requests
        }
      );
    }
  }
}
```

--------------------------------

### Configuration and Command Options

Source: https://v6.docs.astro.build/en/reference/integrations-reference

Provides information on accessing the Astro configuration and understanding the current command being executed.

```APIDOC
## Configuration and Command Options

### Description
Access read-only configuration and identify the current command.

### Method
N/A (Configuration access)

### Endpoint
N/A (Configuration access)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
None

### Response
#### Success Response (200)
- **config** (`AstroConfig`) - A read-only copy of the user-supplied Astro config, resolved before other integrations run.
- **command** (`'dev' | 'build' | 'preview' | 'sync'`) - The current command being executed (`dev`, `build`, `preview`, or `sync`).

#### Response Example
None
```

--------------------------------

### Render Markdown/MDX Body Content in Astro

Source: https://v6.docs.astro.build/en/guides/content-collections

Demonstrates rendering the body content of Markdown or MDX entries fetched from Astro collections. It uses the `render()` function from `astro:content` to get a `<Content />` component and other rendering utilities, allowing the display of raw content within an Astro template.

```typescript
import { getEntry, render } from 'astro:content';


const entry = await getEntry('blog', 'post-1');


const { Content } = await render(entry);
---
<h1>{entry.data.title}</h1>
<p>Published on: {entry.data.published.toDateString()}</p>
<Content />
```

--------------------------------

### Join Comment and Author tables in Astro DB

Source: https://v6.docs.astro.build/en/guides/astro-db

This example demonstrates how to query related data from multiple tables using a SQL join. It uses `innerJoin()` to combine 'Comment' and 'Author' tables based on the 'authorId' and 'id' columns respectively. The result is an array of objects containing both Author and Comment data.

```astro
---
import { db, eq, Comment, Author } from 'astro:db';


const comments = await db.select()
  .from(Comment)
  .innerJoin(Author, eq(Comment.authorId, Author.id));
---


<h2>Comments</h2>


<p>
  {
    comments.map(({ Author, Comment }) => (
    <article>
      <p>Author: {Author.name}</p>
      <p>{Comment.body}</p>
    </article>
  ))
  }
</p>

```

--------------------------------

### Configure Vitest Environment to Node (Astro)

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v6

Shows how to update Vitest configuration to use the 'node' environment instead of 'jsdom' or 'happy-dom' when testing Astro components, as Astro components can no longer be rendered in Vitest client environments.

```javascript
import { defineConfig } from 'vitest/config';


export default defineConfig({
  test: {
    environment: 'jsdom',
    environment: 'node',
  },
});
```

--------------------------------

### Import and Use Zod Coerce for Dates

Source: https://v6.docs.astro.build/en/reference/modules/astro-zod

Demonstrates importing specific Zod utilities like `coerce` directly from `astro/zod`. This example shows how to use `coerce.date()` to parse a date string into a JavaScript `Date` object.

```typescript
import { coerce } from 'astro/zod';


const publishedOn = coerce.date();
const publicationDate = publishedOn.parse("2025-12-03");
```

--------------------------------

### Define Content Collections with Loaders and Zod Schemas

Source: https://v6.docs.astro.build/en/guides/content-collections

Illustrates defining Astro content collections with both custom loaders and Zod schemas. It shows how to use `glob` and `file` loaders to fetch data and defines schemas for blog posts and dog data, ensuring data integrity and providing TypeScript support.

```typescript
import {
  defineCollection
} from 'astro:content';
import { z } from 'astro/zod';
import { glob, file } from 'astro/loaders';


const blog = defineCollection({
  loader: glob({ pattern: "**/*.md", base: "./src/data/blog" }),
  schema: z.object({
    title: z.string(),
    description: z.string(),
    pubDate: z.coerce.date(),
    updatedDate: z.coerce.date().optional(),
  })
});
const dogs = defineCollection({
  loader: file("src/data/dogs.json"),
  schema: z.object({
    id: z.string(),
    breed: z.string(),
    temperament: z.array(z.string()),
  }),
});


export const collections = { blog, dogs };
```

--------------------------------

### Set Environment Variables for Static Deployment with Yarn

Source: https://v6.docs.astro.build/en/guides/deploy/clever-cloud

Configures the build environment for a static Astro application using Yarn. It sets the post-build hook to run the build command, and the pre-build hook to install dependencies and disable Astro telemetry. The webroot is set to '/dist'.

```bash
CC_POST_BUILD_HOOK="yarn build"
CC_PRE_BUILD_HOOK="yarn && yarn run astro telemetry disable"
CC_WEBROOT="/dist"
```

--------------------------------

### Set Environment Variables for Node.js Deployment with Yarn

Source: https://v6.docs.astro.build/en/guides/deploy/clever-cloud

Configures the build environment for a Node.js Astro application using Yarn. It specifies Yarn as the build tool and sets a pre-build hook to install dependencies, disable Astro telemetry, and build the project.

```bash
CC_NODE_BUILD_TOOL="yarn"
CC_PRE_BUILD_HOOK="yarn && yarn run astro telemetry disable && yarn build"
```

--------------------------------

### Configure GitHub Copilot MCP Server for Astro Docs

Source: https://v6.docs.astro.build/en/guides/build-with-ai

This JSON configuration enables GitHub Copilot to access the Astro Docs MCP server. It specifies the server type, URL, and the tools available for documentation retrieval. Ensure this is added to your repository's Copilot coding agent settings.

```json
{
  "mcpServers": {
    "astro-docs": {
      "type": "http",
      "url": "https://mcp.docs.astro.build/mcp",
      "tools": ["mcp__astro-docs__search_astro_docs"]
    }
  }
}
```

--------------------------------

### Define Astro Collection with Custom Loader

Source: https://v6.docs.astro.build/en/reference/content-loader-reference

This example shows how to configure an Astro content collection to use a custom loader. It imports the `defineCollection` function and the custom loader, then passes configuration options to the loader when defining the collection.

```typescript
import { defineCollection } from 'astro:content';
import { feedLoader } from './feed-loader.ts';


const blog = defineCollection({
  loader: feedLoader({
    url: "https://api.example.com/posts",
    apiKey: "my-secret",
  }),
});


export const collections = { blog };
```

--------------------------------

### Define Cache Hint Tags for a Collection (JavaScript)

Source: https://v6.docs.astro.build/en/reference/content-loader-reference

This example demonstrates how to define cache hint tags for a collection of posts, filtered by author. Tags allow for grouping related content and selective cache invalidation. This is useful for managing cache based on dynamic filtering criteria.

```javascript
return {
  /* ... */
  cacheHint: {
    tags: ["posts", `posts-${filter.author}`],
  },
};
```

--------------------------------

### Middleware Chaining with next() Rewrite

Source: https://v6.docs.astro.build/en/guides/middleware

Illustrates how multiple middleware functions can be chained using `sequence()`. When `next()` is called with a path, it rewrites the request in place, and subsequent middleware receives the updated request context without re-execution of the current middleware.

```APIDOC
## PUT /api/users/{id}

### Description
Updates an existing user's information.

### Method
PUT

### Endpoint
/api/users/{id}

### Parameters
#### Path Parameters
- **id** (string) - Required - The unique identifier of the user to update.

#### Request Body
- **username** (string) - Optional - The new username for the user.
- **email** (string) - Optional - The new email address for the user.

### Request Example
```json
{
  "email": "john.doe.updated@example.com"
}
```

### Response
#### Success Response (200)
- **id** (string) - The unique identifier of the updated user.
- **username** (string) - The updated username.
- **email** (string) - The updated email address.

#### Response Example
```json
{
  "id": "user_123abc",
  "username": "johndoe",
  "email": "john.doe.updated@example.com"
}
```
```

--------------------------------

### Add class-based styling for list items in Astro

Source: https://v6.docs.astro.build/en/tutorial/2-pages/4

This code example shows how to dynamically render a list of skills and apply a CSS class named 'skill' to each list item (`<li>`). This enables targeted styling of these elements using CSS. The `skills.map()` function iterates over an array to generate the list.

```astro
<p>My skills are:</p>
<ul>
  {skills.map((skill) => <li class="skill">{skill}</li>)}
</ul>

```

--------------------------------

### Generate Localized URLs with Astro i18n

Source: https://v6.docs.astro.build/en/guides/internationalization

This example demonstrates how to use the `getRelativeLocaleUrl()` helper function from the `astro:i18n` module to create links to pages within your site. These generated links ensure correct, localized routing.

```astro
---
import { getRelativeLocaleUrl } from 'astro:i18n';


// defaultLocale is "es"
const aboutURL = getRelativeLocaleUrl("es", "about");
---


<a href="/get-started/">¡Vamos!</a>
<a href={getRelativeLocaleUrl('es', 'blog')}>Blog</a>
<a href={aboutURL}>Acerca</a>

```

--------------------------------

### Customize CSP Directives

Source: https://v6.docs.astro.build/en/reference/configuration-reference

Allows customization of Content Security Policy (CSP) by defining additional directives beyond the default `script-src` and `style-src`. These directives specify valid sources for various content types and are added to all pages. The example shows how to include `default-src` and `img-src`.

```javascript
import { defineConfig } from 'astro/config';


export default defineConfig({
  security: {
    csp: {
      directives: [
        "default-src 'self'",
        "img-src 'self' https://images.cdn.example.com"
      ]
    }
  }
});
```

--------------------------------

### Configure Multiple JSX Frameworks in Astro

Source: https://v6.docs.astro.build/en/guides/integrations-guide/solid-js

Demonstrates how to configure Astro to use multiple JSX frameworks (Preact, React, Solid) simultaneously. It uses `include` and `exclude` options to specify which files belong to each framework.

```javascript
import { defineConfig } from 'astro/config';
import preact from '@astrojs/preact';
import react from '@astrojs/react';
import svelte from '@astrojs/svelte';
import vue from '@astrojs/vue';
import solid from '@astrojs/solid-js';


export default defineConfig({
  // Enable many frameworks to support all different kinds of components.
  // No `include` is needed if you are only using a single JSX framework!
  integrations: [
    preact({
      include: ['**/preact/*'],
    }),
    react({
      include: ['**/react/*'],
    }),
    solid({
      include: ['**/solid/*', '**/node_modules/@suid/material/**'],
    }),
  ],
});
```

--------------------------------

### nodeApp.render()

Source: https://v6.docs.astro.build/en/reference/adapter-reference

Renders a request using the NodeApp instance, extending the base app.render() to accept Node.js IncomingMessage objects.

```APIDOC
## nodeApp.render()

### Description
Extends `app.render()` to also accept Node.js `IncomingMessage` objects in addition to standard `Request` objects as the first argument. The second argument is an optional object allowing you to control the rendering.

### Method
`nodeApp.render(request: NodeRequest | Request, options?: RenderOptions): Promise<Response>`

### Parameters
- **request** (NodeRequest | Request) - Required - The incoming request object (can be a Node.js `IncomingMessage` or a standard `Request`).
- **options** (RenderOptions) - Optional - An object allowing control over rendering.

### Return Value
- (Promise<Response>) - A Promise that resolves to the Response object.

### Example
```javascript
// Assuming 'nodeApp' is an instance of NodeApp and 'request' is the incoming request
const response = await nodeApp.render(request);
```
```

--------------------------------

### Fetching and Rendering Storyblok Content in Astro

Source: https://v6.docs.astro.build/en/guides/cms/storyblok

This Astro page (`test-post.astro`) demonstrates how to fetch Storyblok content and render it using the Storyblok integration. It uses the `useStoryblokApi` hook to retrieve a specific story (`test-post`) and then passes its content to the `StoryblokComponent` for rendering. It handles fetching draft content in development and published content in production.

```astro
---
import { useStoryblokApi } from '@storyblok/astro'
import StoryblokComponent from '@storyblok/astro/StoryblokComponent.astro'


const storyblokApi = useStoryblokApi()


const { data } = await storyblokApi.get("cdn/stories/test-post", {
  version: import.meta.env.DEV ? "draft" : "published",
});


const content = data.story.content;
---
<StoryblokComponent blok={content} />

```

--------------------------------

### Use CSS variables from frontmatter in Astro <style>

Source: https://v6.docs.astro.build/en/tutorial/2-pages/4

This example demonstrates using Astro's `define:vars` directive to pass variables from the frontmatter script into the `<style>` tag. The `skillColor` variable is defined in the frontmatter and then used as a CSS variable (`--skillColor`) to style the '.skill' class, allowing dynamic theming.

```astro
---
const pageTitle = "About Me";


const identity = {
  firstName: "Sarah",
  country: "Canada",
  occupation: "Technical Writer",
  hobbies: ["photography", "birdwatching", "baseball"],
};


const skills = ["HTML", "CSS", "JavaScript", "React", "Astro", "Writing Docs"];


const happy = true;
const finished = false;
const goal = 3;


const skillColor = "crimson";
---

<style define:vars={{skillColor}}>
  h1 {
    color: purple;
    font-size: 4rem;
  }
  .skill {
    color: green;
    color: var(--skillColor);
    font-weight: bold;
  }
</style>

```

--------------------------------

### Define Supabase Environment Variables in env.d.ts

Source: https://v6.docs.astro.build/en/guides/backend/supabase

Enhance your Astro project's development experience by adding TypeScript typings for your Supabase environment variables in `env.d.ts`. This provides IntelliSense support for `SUPABASE_URL` and `SUPABASE_ANON_KEY`.

```typescript
interface ImportMetaEnv {
  readonly SUPABASE_URL: string
  readonly SUPABASE_ANON_KEY: string
}


interface ImportMeta {
  readonly env: ImportMetaEnv
}
```

--------------------------------

### Configure TypeScript for Environment Variables

Source: https://v6.docs.astro.build/en/guides/cms/ghost

Define the environment variable in a env.d.ts file within the src/ directory to enable IntelliSense for your Content API key. This improves developer experience by providing autocompletion and type checking.

```typescript
interface ImportMetaEnv {
  readonly CONTENT_API_KEY: string;
}
```

--------------------------------

### Format Date from Frontmatter in Astro

Source: https://v6.docs.astro.build/en/tutorial/6-islands/4

Illustrates how to access and format the `pubDate` from a post's frontmatter within an Astro layout. It uses the `toLocaleDateString()` method to convert the `Date` object into a user-friendly string format for display.

```astro
<!-- ... -->
<BaseLayout pageTitle={frontmatter.title}>
    <p>{frontmatter.pubDate.toLocaleDateString()}</p>
    <p><em>{frontmatter.description}</em></p>
    <p>Written by: {frontmatter.author}</p>
    <img src={frontmatter.image.url} width="300" alt={frontmatter.image.alt} />
<!-- ... -->

```

--------------------------------

### Set Last Visit Time in Astro Middleware

Source: https://v6.docs.astro.build/en/guides/sessions

An example of Astro middleware that sets the last visit time in the session. It uses `defineMiddleware` and accesses the session object via `context.session.set()` to store the current date.

```javascript
import { defineMiddleware } from 'astro:middleware';


export const onRequest = defineMiddleware(async (context, next) => {
  context.session?.set('lastVisit', new Date());
  return next();
});

```

--------------------------------

### Configure Xata Environment Variables in .env

Source: https://v6.docs.astro.build/en/guides/backend/xata

Sets up essential environment variables for Xata integration, including the API key and the default branch. These are typically stored in a .env file for security and ease of management.

```env
XATA_API_KEY=hash_key


# Xata branch that will be used
# if there's not a xata branch with
# the same name as your git branch
XATA_BRANCH=main
```

--------------------------------

### Watch Configuration Files with addWatchFile()

Source: https://v6.docs.astro.build/en/reference/integrations-reference

Shows how to use `addWatchFile` to make Astro's dev server reload when specific configuration files change. This is essential for integrations that rely on external config files not automatically watched by Vite. Paths must be absolute.

```javascript
// Must be an absolute path!
addWatchFile('/home/user/.../my-config.json');
addWatchFile(new URL('./ec.config.mjs', config.root));
```

--------------------------------

### Storyblok BlogPostList Component in Astro

Source: https://v6.docs.astro.build/en/guides/cms/storyblok

Fetches and displays a list of blog posts using the Storyblok API. It conditionally fetches draft or published versions based on the environment. Includes storyblokEditable for in-editor editing.

```astro
---
import { storyblokEditable } from '@storyblok/astro'
import { useStoryblokApi } from '@storyblok/astro'


const storyblokApi = useStoryblokApi();


const { data } = await storyblokApi.get('cdn/stories', {
  version: import.meta.env.DEV ? "draft" : "published",
  content_type: 'blogPost',
})


const posts = data.stories.map(story => {
  return {
    title: story.content.title,
    date: new Date(story.published_at).toLocaleDateString("en-US", {dateStyle: "full"}),
    description: story.content.description,
    slug: story.full_slug,
  }
})


const { blok } = Astro.props
---


<ul {...storyblokEditable(blok)}>
  {posts.map(post => (
    <li>
      <time>{post.date}</time>
      <a href={post.slug}>{post.title}</a>
      <p>{post.description}</p>
    </li>
  ))}
</ul>

```

--------------------------------

### Deploy Astro Site via Fleek CLI

Source: https://v6.docs.astro.build/en/guides/deploy/fleek

Deploys the configured Fleek site. This command uploads the static files generated by the build process to Fleek's decentralized network.

```bash
fleek sites deploy
```

--------------------------------

### Generate Dynamic Post Pages in Astro

Source: https://v6.docs.astro.build/en/guides/cms/ghost

Dynamically generates individual pages for each blog post fetched from Ghost CMS. It uses getStaticPaths to define routes based on post slugs and passes post data as props to the page template.

```astro
--- 
import { ghostClient } from '../../lib/ghost';


export async function getStaticPaths() {
    const posts = await ghostClient.posts
        .browse({
            limit: 'all',
        })
        .catch((err) => {
            console.error(err);
        });


    return posts.map((post) => {
        return {
            params: {
                slug: post.slug,
            },
            props: {
                post: post,
            },
        };
    });
}


const { post } = Astro.props;
---
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>{post.title}</title>
    </head>
    <body>
        <img src={post.feature_image} alt={post.title} />


        <h1>{post.title}</h1>
        <p>{post.reading_time} min read</p>


        <Fragment set:html={post.html} />
    </body>
</html>
```

--------------------------------

### Dynamically Generate Tag Pages with Content Collections (Astro)

Source: https://v6.docs.astro.build/en/tutorial/6-islands/4

This snippet shows how to dynamically generate pages for each tag based on blog post collections. It uses `getCollection('blog')` to fetch all posts, extracts unique tags, and then generates static paths for each tag. For each tag, it filters posts and passes them as props to the page, rendering a list of blog posts associated with that tag.

```astro
---
import { getCollection } from "astro:content";
import BaseLayout from "../../layouts/BaseLayout.astro";
import BlogPost from "../../components/BlogPost.astro";


export async function getStaticPaths() {
  const allPosts = await getCollection("blog");
  const uniqueTags = [...new Set(allPosts.map((post) => post.data.tags).flat())];


  return uniqueTags.map((tag) => {
    const filteredPosts = allPosts.filter((post) =>
      post.data.tags.includes(tag)
    );
    return {
      params: { tag },
      props: { posts: filteredPosts },
    };
  });
}


const { tag } = Astro.params;
const { posts } = Astro.props;
---


<BaseLayout pageTitle={tag}>
  <p>Posts tagged with {tag}</p>
  <ul>
    { posts.map((post) => <BlogPost url={`/posts/${post.id}/`} title={post.data.title} />) }
  </ul>
</BaseLayout>
```

--------------------------------

### Fetch DatoCMS Content in Astro using GraphQL

Source: https://v6.docs.astro.build/en/guides/cms/datocms

This code demonstrates how to fetch content, specifically the 'title' field of the 'home' page, from DatoCMS using its GraphQL API within an Astro component. It utilizes the fetch API and includes the necessary headers for authentication and content type.

```astro
---
const response = await fetch('https://graphql.datocms.com/', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    Accept: 'application/json',
    Authorization: `Bearer ${import.meta.env.DATOCMS_API_KEY}`,
  },
  body: JSON.stringify({
    query: `query Homepage {
          home {
            title
          }
        }`,
  }),
});


const json = await response.json();
const data = json.data.home;
---


<h1>{data.title}</h1>
```

--------------------------------

### Enable Experimental Static Headers with CSP in Astro Netlify

Source: https://v6.docs.astro.build/en/guides/integrations-guide/netlify

This code snippet demonstrates how to enable the `experimentalStaticHeaders` option in the Astro Netlify adapter and configure Content Security Policy (CSP). When `experimentalStaticHeaders` is true, the adapter saves static headers, such as CSP directives, in the Framework API config file for Netlify, avoiding the need for meta elements.

```javascript
import {
  defineConfig
} from 'astro/config';
import netlify from '@astrojs/netlify';


export default defineConfig({
  security: {
    csp: true
  },
  adapter: netlify({
    experimentalStaticHeaders: true
  })
});
```

--------------------------------

### Call Custom Markdoc Function in Content

Source: https://v6.docs.astro.build/en/guides/integrations-guide/markdoc

An example showing how to call the custom 'getCountryEmoji' function within Markdoc content. This allows for embedding dynamic elements, like country flags, directly into your documentation or articles.

```markdoc
¡Hola {% getCountryEmoji("spain") %}!
```

--------------------------------

### Handle App Initialization on Server (JavaScript)

Source: https://v6.docs.astro.build/en/reference/dev-toolbar-app-reference

Registers a callback that executes when a specific toolbar app is initialized on the server. This ensures that subsequent operations targeting the app are performed after it's ready, using `toolbar.onAppInitialized`.

```javascript
'astro:server:setup': ({ toolbar }) => {
  toolbar.onAppInitialized('my-app', () => {
    console.log('The app is now initialized!');
  });
},
```

--------------------------------

### Call Astro Action with Error Handling in JavaScript

Source: https://v6.docs.astro.build/en/reference/modules/astro-actions

Demonstrates how to call an Astro action from the client-side using the 'actions' object and handle potential errors. It shows an example of incrementing a like count and checking for errors.

```javascript
---
---


<!-- your template -->


<script>
import { actions } from 'astro:actions';


const post = document.querySelector('article');
const button = document.querySelector('button');
button?.addEventListener('click', async () => {
  const { data: updatedLikes, error } = await actions.likePost({ postId: post?.id });
  if (error) {
    /* handle errors */
  }
})
</script>

```

--------------------------------

### Get all entries as an array in Astro

Source: https://v6.docs.astro.build/en/reference/content-loader-reference

The `values()` method provides all content entries from a collection as a flat array of `DataEntry` objects. This is a convenient way to access the data of all entries when you don't need their specific keys immediately.

```typescript
import { collection } from 'astro:content';

const allEntryValues = await collection('docs').values();
console.log(allEntryValues);
```

--------------------------------

### Login to Fleek Account via CLI

Source: https://v6.docs.astro.build/en/guides/deploy/fleek

Logs the user into their Fleek account from the terminal. This is a prerequisite for using other Fleek CLI commands.

```bash
fleek login
```

--------------------------------

### Configure Environment Variable IntelliSense in Astro

Source: https://v6.docs.astro.build/en/guides/cms/strapi

This TypeScript code defines the structure for environment variables in Astro, specifically for the STRAPI_URL. Creating an env.d.ts file in the src/ directory provides IntelliSense for your environment variables, improving developer experience and reducing errors.

```typescript
interface ImportMetaEnv {
  readonly STRAPI_URL: string;
}
```

--------------------------------

### Astro Sign-in Form with Token Check

Source: https://v6.docs.astro.build/en/guides/backend/supabase

Provides a sign-in form for users, submitting credentials to /api/auth/signin. It checks for existing access and refresh tokens in cookies and redirects to the dashboard if found. Requires the Layout component.

```astro
---
import Layout from "../layouts/Layout.astro";


const { cookies, redirect } = Astro;


const accessToken = cookies.get("sb-access-token");
const refreshToken = cookies.get("sb-refresh-token");


if (accessToken && refreshToken) {
  return redirect("/dashboard");
}
---


<Layout title="Sign in">
  <h1>Sign in</h1>
  <p>New here? <a href="/register">Create an account</a></p>
  <form action="/api/auth/signin" method="post">
    <label for="email">Email</label>
    <input type="email" name="email" id="email" />
    <label for="password">Password</label>
    <input type="password" name="password" id="password" />
    <button type="submit">Login</button>
  </form>
</Layout>
```

--------------------------------

### Apply Fontsource Font to HTML Element

Source: https://v6.docs.astro.build/en/guides/fonts

Applies a font managed by Fontsource to an HTML element using CSS. This example uses the 'Twinkle Star' font for h1 elements.

```css
h1 {
  font-family: "Twinkle Star", cursive;
}
```

--------------------------------

### Configure Rehype Plugin for Heading IDs (Astro)

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v6

Demonstrates how to configure Astro's markdown settings to use the rehypeHeadingIds plugin, including the deprecated `headingIdCompat` option and its removal in favor of direct plugin usage.

```javascript
import { defineConfig } from 'astro/config';
import { rehypeHeadingIds } from '@astrojs/markdown-remark';
import { otherPluginThatReliesOnHeadingIDs } from 'some/plugin/source';


export default defineConfig({
  markdown: {
    rehypePlugins: [
      [rehypeHeadingIds, { headingIdCompat: true }],
      [rehypeHeadingIds],
      otherPluginThatReliesOnHeadingIDs,
    ],
  },
});
```

--------------------------------

### Configure @astrojs/node Adapter for Static Headers

Source: https://v6.docs.astro.build/en/guides/integrations-guide/node

Enable the `experimentalStaticHeaders` option to serve headers from prerendered pages using the `Response` object. This is particularly useful for features like Content Security Policy (CSP).

```javascript
import { defineConfig } from 'astro/config';
import node from '@astrojs/node';


export default defineConfig({
  security: {
    csp: true
  },
  adapter: node({
    mode: 'standalone',
    experimentalStaticHeaders: true,
  })
});
```

--------------------------------

### Basic Middleware for Action Results in Astro

Source: https://v6.docs.astro.build/en/guides/actions

An example of Astro middleware using getActionContext() to manually handle action results. This middleware intercepts action calls, executes the action handler, and uses setActionResult() to make the result available via Astro.getActionResult().

```javascript
import { defineMiddleware } from 'astro:middleware';
import { getActionContext } from 'astro:actions';


export const onRequest = defineMiddleware(async (context, next) => {
  const { action, setActionResult, serializeActionResult } = getActionContext(context);
  if (action?.calledFrom === 'form') {
    const result = await action.handler();
    // ... handle the action result
    setActionResult(action.name, serializeActionResult(result));
  }
  return next();
});
```

--------------------------------

### MarkdownPostLayout Astro Component

Source: https://v6.docs.astro.build/en/tutorial/5-astro-api/3

This Astro component defines the layout for displaying blog posts. It imports a `BaseLayout` and uses frontmatter properties to render the post's title, description, publication date, author, and image. It also dynamically renders tags with links and includes a slot for the post content. Basic CSS is included for styling.

```astro
---
import BaseLayout from './BaseLayout.astro';
const { frontmatter } = Astro.props;
---
<BaseLayout pageTitle={frontmatter.title}>
  <p><em>{frontmatter.description}</em></p>
  <p>{frontmatter.pubDate.toString().slice(0,10)}</p>


  <p>Written by: {frontmatter.author}</p>


  <img src={frontmatter.image.url} width="300" alt={frontmatter.image.alt} />


  <div class="tags">
    {frontmatter.tags.map((tag: string) => (
      <p class="tag"><a href={`/tags/${tag}`}>{tag}</a></p>
    ))}
  </div>


  <slot />
</BaseLayout>
<style>
  a {
    color: #00539F;
  }


  .tags {
    display: flex;
    flex-wrap: wrap;
  }


  .tag {
    margin: 0.25em;
    border: dotted 1px #a1a1a1;
    border-radius: .5em;
    padding: .5em 1em;
    font-size: 1.15em;
    background-color: #F8FCFD;
  }
</style>
```

--------------------------------

### Fetch Blog Posts using getCollection() (Astro)

Source: https://v6.docs.astro.build/en/tutorial/6-islands/4

This snippet demonstrates replacing `import.meta.glob()` with `getCollection('blog')` for fetching blog post data. This is the standard method for accessing content within an Astro collection. It also shows how to access frontmatter data via the `data` property instead of `frontmatter`.

```astro
---
import { getCollection } from "astro:content";
import BaseLayout from "../layouts/BaseLayout.astro";
import BlogPost from "../components/BlogPost.astro";


const pageTitle = "My Astro Learning Blog";
const allPosts = Object.values(import.meta.glob("../pages/posts/*.md", { eager: true }));
const allPosts = await getCollection("blog");
---
```

--------------------------------

### Build a Custom Astro Content Loader

Source: https://v6.docs.astro.build/en/reference/content-loader-reference

This example demonstrates how to create a custom content loader in Astro. It fetches data from a feed URL, parses it using Zod for validation, and stores it in the Astro content store. This loader requires a URL and an API key for fetching data and defines a schema for the feed items.

```typescript
import type { Loader } from 'astro/loaders';
import { z } from 'astro/zod';
import { loadFeedData } from "./feed.js";


// 2. Define any options that your loader needs
export function myLoader(options: { url: string, apiKey: string }) {
  const feedUrl = new URL(options.url);
  // 3. Return a loader object
  return {
    name: "feed-loader",
    load: async ({ store, parseData }) => {
      const feed = await loadFeedData(feedUrl, options.apiKey);


      store.clear();


      for (const item of feed.items) {
        const id = item.guid;
        const data = await parseData({
          id,
          data: item,
        });
        store.set({
          id,
          data,
        });
      }
    },
    // 4. Define the schema of an entry.
    schema: z.object({
      // ...
    })
  } satisfies Loader;
}
```

--------------------------------

### Configure Svelte IDE Support with svelte.config.js

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v2

Astro v2.0 requires a `svelte.config.js` file for IDE autocompletion when using the `@astrojs/svelte` integration. This file should be placed in the root of your project. For new installations, `astro add svelte` will create this file automatically.

```javascript
import { vitePreprocess } from '@astrojs/svelte';


export default {
  preprocess: vitePreprocess(),
};
```

--------------------------------

### Sign In User Endpoint (Astro/TypeScript)

Source: https://v6.docs.astro.build/en/guides/backend/supabase

This endpoint handles user sign-in. It accepts POST requests with email and password, then uses the Supabase SDK to authenticate the user and set session cookies. Ensure `export const prerender = false;` if using `static` rendering mode.

```typescript
// With `output: 'static'` configured:
// export const prerender = false;
import type { APIRoute } from "astro";
import { supabase } from "../../../lib/supabase";


export const POST: APIRoute = async ({ request, cookies, redirect }) => {
  const formData = await request.formData();
  const email = formData.get("email")?.toString();
  const password = formData.get("password")?.toString();


  if (!email || !password) {
    return new Response("Email and password are required", { status: 400 });
  }


  const { data, error } = await supabase.auth.signInWithPassword({
    email,
    password,
  });


  if (error) {
    return new Response(error.message, { status: 500 });
  }


  const { access_token, refresh_token } = data.session;
  cookies.set("sb-access-token", access_token, {
    path: "/",
  });
  cookies.set("sb-refresh-token", refresh_token, {
    path: "/",
  });
  return redirect("/dashboard");
};

```

--------------------------------

### Display Blog Posts Index Page in Astro

Source: https://v6.docs.astro.build/en/guides/cms/apostrophecms

Astro component to display a list of blog posts. It fetches page and piece data from ApostropheCMS and renders titles, publication dates, author names, and links to individual posts.

```astro
---
import dayjs from 'dayjs';


const { page, pieces } = Astro.props.aposData;
---


<section class="bp-content">
  <h1>{ page.title }</h1>


  <h2>Blog Posts</h2>


  {pieces.map(piece => (
    <h4>
      Released On { dayjs(piece.publicationDate).format('MMMM D, YYYY') }
    </h4>
    <h3>
      <a href={ piece._url }>{ piece.title }</a>
    </h3>
    <h4>{ piece.authorName }</h4>
  ))}
</section>
```

--------------------------------

### Astro Pagination Implementation

Source: https://v6.docs.astro.build/en/guides/routing

Demonstrates how to implement pagination in Astro using the `paginate()` function. It shows how to define static paths with pagination and how to access paginated data within the component. This is useful for handling large datasets and splitting them into manageable pages.

```astro
---
export function getStaticPaths({ paginate }) {
  const astronautPages = [
    { astronaut: "Neil Armstrong" },
    { astronaut: "Buzz Aldrin" },
    { astronaut: "Sally Ride" },
    { astronaut: "John Glenn" },
  ];

  // Generate pages from our array of astronauts, with 2 to a page
  return paginate(astronautPages, { pageSize: 2 });
}
// All paginated data is passed on the "page" prop
const { page } = Astro.props;
---
<!-- Display the current page number. `Astro.params.page` can also be used! -->
<h1>Page {page.currentPage}</h1>
<ul>
  <!-- List the array of astronaut info -->
  {page.data.map(({ astronaut }) => <li>{astronaut}</li>)}
</ul>

```

--------------------------------

### Rebuild Flotiq TypeScript SDK with npm

Source: https://v6.docs.astro.build/en/guides/cms/flotiq

Rebuilds the `flotiq-api-ts` package using npm to ensure the project reflects the latest content type model updates from Flotiq. This command is necessary after changing content type structures.

```bash
npm rebuild flotiq-api-ts

```

--------------------------------

### Apply CSS class to Astro Child Component

Source: https://v6.docs.astro.build/en/guides/styling

Shows how to import and use a child Astro component, applying a CSS class defined in the parent's `<style>` block. The example uses a `.red` class to style the content passed to the child component.

```astro
---
import MyComponent from "../components/MyComponent.astro"
---
<style>
  .red {
    color: red;
  }
</style>
<MyComponent class="red">This will be red!</MyComponent>
```

--------------------------------

### Define Table with Reference Column

Source: https://v6.docs.astro.build/en/guides/astro-db

Demonstrates how to define table references using `primaryKey` and `references` properties. This example shows an `Author` table with a primary key `id` and a `Comment` table where `authorId` references the `Author` table's `id`, establishing a one-to-many relationship.

```typescript
const Author = defineTable({
  columns: {
    id: column.number({ primaryKey: true }),
    name: column.text(),
  }
});


const Comment = defineTable({
  columns: {
    authorId: column.number({ references: () => Author.columns.id }),
    body: column.text(),
  }
});
```

--------------------------------

### Fetch Single Blog Post by Slug in Astro

Source: https://v6.docs.astro.build/en/guides/cms/flotiq

Fetches a single blog post from Flotiq based on its slug parameter. It includes logic to redirect to a 404 page if the post is not found. This is useful for on-demand rendering of individual posts in SSR mode.

```astro
---
import type { Blogpost } from "flotiq-api-ts";
import { flotiq } from "../../lib/flotiq";


const { slug } = Astro.params;
let post: Blogpost;


const blogpostList = await flotiq.BlogpostAPI.list({
  filters: JSON.stringify({
    slug: {
      type: 'equals',
      filter: slug,
    }
  }),
  limit: 1
});


if (blogpostList.data?.[0]) {
  post = blogpostList.data[0]
} else {
  return Astro.redirect('/404');
}
---

```

--------------------------------

### Prefetch Configuration

Source: https://v6.docs.astro.build/en/reference/configuration-reference

Configure link prefetching to enhance page transition speed.

```APIDOC
## Prefetch Options

#### Description
Enable prefetching for links to provide faster page transitions. This is enabled by default when using `<ClientRouter />`.

#### Type
`boolean | object`

#### Usage
Add the `data-astro-prefetch` attribute to `<a>` links to enable prefetching for specific links.
```html
<a href="/about" data-astro-prefetch>About</a>
```

### `prefetch.prefetchAll`

#### Description
Enables prefetching for all links, regardless of the `data-astro-prefetch` attribute. Defaults to `true` when using `<ClientRouter />`, otherwise `false`.

#### Type
`boolean`

#### Example
```json
{
  "prefetch": {
    "prefetchAll": true
  }
}
```

#### Usage
Set `data-astro-prefetch="false"` on individual links to disable prefetching for them when `prefetchAll` is true.
```html
<a href="/about" data-astro-prefetch="false">About</a>
```

### `prefetch.defaultStrategy`

#### Description
Sets the default prefetch strategy when `data-astro-prefetch` is used without a value.

#### Type
`'tap' | 'hover' | 'viewport' | 'load'`

#### Default
`'hover'`

#### Strategies
*   `'tap'`: Prefetch just before clicking.
*   `'hover'`: Prefetch on hover or focus (default).
*   `'viewport'`: Prefetch as links enter the viewport.
*   `'load'`: Prefetch all links after the page loads.

#### Example
```html
<a href="/about" data-astro-prefetch="viewport">About</a>
```
```

--------------------------------

### Get Action Path for Fetch API with JavaScript

Source: https://v6.docs.astro.build/en/reference/modules/astro-actions

Generates a URL path for an action, allowing it to be called directly as a fetch() operation. This utility accepts an action and returns its URL, enabling custom headers and options.

```javascript
import { actions, getActionPath } from 'astro:actions'


await fetch(getActionPath(actions.like), {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    Authorization: 'Bearer YOUR_TOKEN'
  },
  body: JSON.stringify({ id: 'YOUR_ID' }),
  keepalive: true
})

```

--------------------------------

### Using context.rewrite() in Middleware

Source: https://v6.docs.astro.build/en/guides/middleware

Demonstrates how to use `context.rewrite()` within middleware to change the rendered page content without a user-visible redirect. This method triggers a new rendering phase and re-executes middleware.

```APIDOC
## POST /api/users

### Description
Creates a new user in the system.

### Method
POST

### Endpoint
/api/users

### Parameters
#### Query Parameters
- **limit** (integer) - Optional - The maximum number of users to return.

#### Request Body
- **username** (string) - Required - The desired username for the new user.
- **email** (string) - Required - The email address of the new user.
- **password** (string) - Required - The password for the new user.

### Request Example
```json
{
  "username": "johndoe",
  "email": "john.doe@example.com",
  "password": "securepassword123"
}
```

### Response
#### Success Response (201)
- **id** (string) - The unique identifier for the newly created user.
- **username** (string) - The username of the created user.
- **email** (string) - The email address of the created user.

#### Response Example
```json
{
  "id": "user_123abc",
  "username": "johndoe",
  "email": "john.doe@example.com"
}
```
```

--------------------------------

### Get all entry keys in Astro

Source: https://v6.docs.astro.build/en/reference/content-loader-reference

The `keys()` method returns an array of strings, where each string is the unique identifier (key) for an entry in the collection. This is helpful when you need a list of all available entry IDs without fetching the full entry data.

```typescript
import { collection } from 'astro:content';

const entryKeys = await collection('pages').keys();
console.log(entryKeys);
```

--------------------------------

### Define a LiveLoader in Astro

Source: https://v6.docs.astro.build/en/reference/content-loader-reference

Demonstrates how to define a LiveLoader object in Astro, including its name and methods for loading collections and entries. This example uses TypeScript for type safety with generic parameters for data, entry filters, collection filters, and error types.

```typescript
import type {
	LiveLoader,
	LoadCollectionContext,
	LoadEntryContext,
	LiveDataCollection,
	LiveDataEntry,
	CacheHint,
} from '@astrojs/content';

type BlogPost = {
	id: string;
	title: string;
	body: string;
};

type BlogEntryFilter = {
	tag?: string;
};

type BlogCollectionFilter = {
	limit?: number;
};

type BlogError = Error & {
	customMessage?: string;
};

const blogLoader: LiveLoader<BlogPost, BlogEntryFilter, BlogCollectionFilter, BlogError> = {
	name: 'blog',

	async loadCollection(context: LoadCollectionContext<BlogCollectionFilter>): Promise<LiveDataCollection<BlogPost> | { error: BlogError }> {
		// Implementation to load a collection of blog posts
		// This would typically involve fetching data from a CMS or API
		const posts: BlogPost[] = []; // Replace with actual data fetching
		const collection: LiveDataCollection<BlogPost> = { entries: posts };
		return collection;
	},

	async loadEntry(context: LoadEntryContext<BlogEntryFilter>): Promise<LiveDataEntry<BlogPost> | undefined | { error: BlogError }> {
		// Implementation to load a single blog post by its ID or filter
		// This would typically involve fetching data from a CMS or API
		const post: BlogPost | undefined = undefined; // Replace with actual data fetching
		if (!post) {
			return undefined;
		}
		const entry: LiveDataEntry<BlogPost> = { id: post.id, data: post };
		return entry;
	},
};

export default blogLoader;

```

--------------------------------

### Adding Renderers Manually

Source: https://v6.docs.astro.build/en/reference/container-reference

Demonstrates how to manually import and add server and client renderers to the Astro container when helper functions are unavailable.

```APIDOC
## Adding a renderer manually

### Description
When the container is called at runtime, or inside other “shells”, the `astro:container` virtual module’s helper functions are not available. You must import the necessary server and client renderers manually and store them inside the container using `addServerRenderer` and `addClientRenderer`.

Server renderers are required to build your project, and must be stored in the container for every framework used. Client renderers are additionally needed to any hydrate client-side components using `client:*` directives.

Only one import statement is needed per framework. Importing a renderer makes both the server and client renderers available to your container. However, **server renderers must be added to your container before client renderers**. This allows your entire container to render first, and then hydrate any interactive components.

### Method
`addServerRenderer`, `addClientRenderer`

### Example
```javascript
import reactRenderer from "@astrojs/react/server.js";
import vueRenderer from "@astrojs/vue/server.js";
import mdxRenderer from "@astrojs/mdx/server.js";


const container = await experimental_AstroContainer.create();
container.addServerRenderer({ renderer: vueRenderer });
container.addServerRenderer({ renderer: mdxRenderer });


container.addServerRenderer({ renderer: reactRenderer });
container.addClientRenderer({ name: "@astrojs/react", entrypoint: "@astrojs/react/client.js" });
```
```

--------------------------------

### Define Astro DB Schema with `defineDb` and `defineTable`

Source: https://v6.docs.astro.build/en/guides/astro-db

Defines a database schema for Astro DB using `defineDb` and `defineTable`. This example sets up a 'Pets' table with 'name' and 'species' columns, both of type text. This schema can then be used in configuration and seed files.

```typescript
import { defineDb, defineTable, column } from 'astro:db';


export const Pets = defineTable({
  columns: {
    name: column.text(),
    species: column.text(),
  },
});


export default defineDb({ tables: { Pets } });
```

--------------------------------

### Import Prism Component from @astrojs/prism

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

This code snippet shows how to import the Prism component from the `@astrojs/prism` package. Previously included in `astro/components`, it has been moved to a dedicated package to keep Astro's core lean. This import statement is necessary for using Prism syntax highlighting in your Astro project.

```astro
---
import { Prism } from '@astrojs/prism';
---
```

--------------------------------

### Update async access for SSRManifest mappings and drivers (Astro Adapter API)

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v6

Astro 6.0 introduces asynchronous methods for `serverIslandMappings` and `sessionDriver` in the `SSRManifest`. You must now use `await` when accessing these properties.

```javascript
const mappings = manifest.serverIslandMappings;
const driver = manifest.sessionDriver;
```

```javascript
const mappings = await manifest.serverIslandMappings?.();
const driver = await manifest.sessionDriver?.();
```

--------------------------------

### Nuxt Link Component to Astro Anchor Tag

Source: https://v6.docs.astro.build/en/guides/migrate-to-astro/from-nuxtjs

Shows how to replace Nuxt's `<NuxtLink>` component with standard HTML `<a>` tags in Astro for basic navigation. It also includes an example of creating a custom Astro `<Link>` component for more advanced use cases.

```astro
<NuxtLink to="/blog">Blog</Link>
<a href="/blog">Blog</a>
```

```astro
--- 
const { to } = Astro.props
--- 
<a href={to}><slot /></a>
```

--------------------------------

### Access Adapter Arguments in createExports (JavaScript)

Source: https://v6.docs.astro.build/en/reference/adapter-reference

Demonstrates how to access build-time configuration arguments passed to `createExports`, such as the path to Astro-generated assets.

```javascript
import { App } from 'astro/app';


export function createExports(manifest, args) {
  const assetsPath = args.assets;


  const handler = (event, context) => {
    // ...
  };


  return { handler };
}
```

--------------------------------

### Push Database Configuration Changes (`astro db push`)

Source: https://v6.docs.astro.build/en/guides/integrations-guide/db

Safely pushes database configuration changes to your project database. It checks for data loss risks and guides on migration steps. The `--force-reset` flag can be used to reset all production data if a breaking schema change is required.

```bash
astro db push
astro db push --force-reset
```

--------------------------------

### Rebuild Flotiq TypeScript SDK with pnpm

Source: https://v6.docs.astro.build/en/guides/cms/flotiq

Rebuilds the `flotiq-api-ts` package using pnpm to ensure the project reflects the latest content type model updates from Flotiq. This command is necessary after changing content type structures.

```bash
pnpm rebuild flotiq-api-ts

```

--------------------------------

### External Image Service Implementation in TypeScript

Source: https://v6.docs.astro.build/en/reference/image-service-reference

An example of an external image service implementation in TypeScript for Astro. This service defines how to validate image transformation options, generate the final image URL, and set HTML attributes for the `<img>` tag. It demonstrates integrating with a hypothetical CDN service.

```typescript
import type { ExternalImageService, ImageTransform, AstroConfig } from "astro";


const service: ExternalImageService = {
  validateOptions(options: ImageTransform, imageConfig: AstroConfig['image']) {
    const serviceConfig = imageConfig.service.config;


    // Enforce the user set max width.
    if (options.width && options.width > serviceConfig.maxWidth) {
      console.warn(`Image width ${options.width} exceeds max width ${serviceConfig.maxWidth}. Falling back to max width.`);
      options.width = serviceConfig.maxWidth;
    }


    return options;
  },
  getURL(options, imageConfig) {
    return `https://mysupercdn.com/${options.src}?q=${options.quality}&w=${options.width}&h=${options.height}`;
  },
  getHTMLAttributes(options, imageConfig) {
    const { src, format, quality, ...attributes } = options;
    return {
      ...attributes,
      loading: options.loading ?? 'lazy',
      decoding: options.decoding ?? 'async',
    };
  }
};




export default service;

```

--------------------------------

### Astro Configuration with Site, Base, and Trailing Slash

Source: https://v6.docs.astro.build/en/guides/configuring-astro

This code snippet shows how to configure Astro with specific deployment settings. It includes options for `site` (deployment domain), `base` (project root path), and `trailingSlash` (handling of trailing slashes in URLs), which are crucial for SEO and correct URL generation.

```javascript
import { defineConfig } from "astro/config";


export default defineConfig({
  site: "https://www.example.com",
  base: "/docs",
  trailingSlash: "always",
});
```

--------------------------------

### Pass Named Slot Content to Astro Component

Source: https://v6.docs.astro.build/en/reference/container-reference

This example shows how to pass content to named slots ('header' and 'footer') of an Astro component using the `slots` option in `renderToString`. Each named slot receives its corresponding content as a string value.

```javascript
import Card from "../src/components/Card.astro";


const result = await container.renderToString(Card, {
  slots: {
    header: "Header content",
    footer: "Footer"
  }
});
```

--------------------------------

### Get all entries as key-value pairs in Astro

Source: https://v6.docs.astro.build/en/reference/content-loader-reference

The `entries()` method retrieves all content entries from a collection as an array of `[id: string, DataEntry]` pairs. This is useful for iterating through all available content and accessing both the entry's identifier and its data.

```typescript
import { collection } from 'astro:content';

const allEntries = await collection('blog').entries();
console.log(allEntries);
```

--------------------------------

### Astro Dashboard with Authentication Check

Source: https://v6.docs.astro.build/en/guides/backend/supabase

A protected dashboard page that verifies the presence and validity of 'sb-access-token' and 'sb-refresh-token' cookies. If tokens are missing or invalid, it redirects to the sign-in page. It uses the supabase client to set the session.

```astro
---
import Layout from "../layouts/Layout.astro";
import { supabase } from "../lib/supabase";


const accessToken = Astro.cookies.get("sb-access-token");
const refreshToken = Astro.cookies.get("sb-refresh-token");


if (!accessToken || !refreshToken) {
  return Astro.redirect("/signin");
}


let session;
try {
  session = await supabase.auth.setSession({
    refresh_token: refreshToken.value,
    access_token: accessToken.value,
  });
  if (session.error) {
    Astro.cookies.delete("sb-access-token", {
      path: "/",
    });
    Astro.cookies.delete("sb-refresh-token", {
      path: "/",
    });
    return Astro.redirect("/signin");
  }
} catch (error) {
  Astro.cookies.delete("sb-access-token", {
    path: "/",
  });
  Astro.cookies.delete("sb-refresh-token", {
    path: "/",
  });
  return Astro.redirect("/signin");
}


const email = session.data.user?.email;
---
<Layout title="dashboard">
  <h1>Welcome {email}</h1>
  <p>We are happy to see you here</p>
  <form action="/api/auth/signout">
    <button type="submit">Sign out</button>
  </form>
</Layout>
```

--------------------------------

### Markdown Heading ID Generation in Astro

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v6

Provides an example of a Markdown heading that might have its ID generation behavior changed in Astro 6.0. Trailing hyphens are no longer stripped by default, which may require updating anchor links if they previously relied on this behavior.

```markdown
## My Heading with Special Chars-
```

--------------------------------

### Get Original Image Query Parameters (JavaScript)

Source: https://v6.docs.astro.build/en/reference/modules/astro-assets

Retrieves image dimensions (width, height, format) from a `URLSearchParams` object. Returns `undefined` if any required parameters are missing or invalid.

```javascript
import { getOrigQueryParams } from 'astro/assets/utils';


const url = new URL('https://example.com/image.jpg?width=800&height=600&format=jpg');
const origParams = getOrigQueryParams(url.searchParams);
// Example value:
// {
//    width: 800,
//    height: 600,
//    format: 'jpg'
// }
```

--------------------------------

### Receive Message on Server from Client (JavaScript)

Source: https://v6.docs.astro.build/en/reference/dev-toolbar-app-reference

Registers a callback on the server to listen for messages sent from a client-side toolbar app. This uses the `toolbar.on` method within the `astro:server:setup` hook, specifying the event name.

```javascript
'astro:server:setup': ({ toolbar }) => {
  toolbar.on('my-app:my-message', (data) => {
    console.log(data.message);
  });
},
```

--------------------------------

### Manual Skew Protection Header for Fetch Requests

Source: https://v6.docs.astro.build/en/guides/integrations-guide/netlify

When making custom fetch requests to your Astro site on Netlify, manually include the skew protection header using the `DEPLOY_ID` environment variable. This ensures content consistency during deployments.

```javascript
const response = await fetch('/api/endpoint', {
  headers: {
    'X-Netlify-Deploy-ID': import.meta.env.DEPLOY_ID,
  },
});
```

--------------------------------

### Display Individual Blog Post in Astro (SSG)

Source: https://v6.docs.astro.build/en/guides/cms/flotiq

Create a template for individual blog post pages using Astro's static site generation. This code snippet fetches post data via `Astro.props` (populated by `getStaticPaths`) and displays the post's title and content.

```astro
---
import type { Blogpost } from "flotiq-api-ts";
import { flotiq } from "../../lib/flotiq";


export async function getStaticPaths() {
  const posts = await flotiq.BlogpostAPI.list();
  return posts.data?.map((post) => ({
    params: { slug: post.slug },
    props: post
  })) || []
}
const post: Blogpost = Astro.props;
---
<html lang="en">
  <title>{post.title}</title>
  <body>
    <h1>{post.title}</h1>
    <div set:html={post.content}/>
  </body>
</html>

```

--------------------------------

### Use Astro Layout in about.astro

Source: https://v6.docs.astro.build/en/guides/migrate-to-astro/from-gatsby

This Astro component (`about.astro`) demonstrates using the `Layout.astro` component for a different page. Similar to `index.astro`, it imports the layout and passes the `title` and `pathname` props. This setup ensures consistent layout and conditional header rendering across different pages.

```astro
---
import Layout from '../layouts/Layout.astro';
const pagePathname = Astro.url.pathname
---
<Layout title="About" pathname={pagePathname}>
    <p>About</p>
</Layout>
```

--------------------------------

### Configure Import Aliases in tsconfig.json

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

Astro v0.21+ allows configuring import aliases directly within the `tsconfig.json` file. This enables cleaner import paths for components and other modules.

```json
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/components/*": ["src/components/*"]
    }
  }
}
```

--------------------------------

### Astro Cloudflare Adapter Build Configuration for Pages

Source: https://v6.docs.astro.build/en/guides/integrations-guide/cloudflare

Sets up the Astro build output directories in `astro.config.mjs` for deployment to Cloudflare Pages. It specifies the client-side output and the server-side worker file location, which are necessary for Pages to correctly route requests.

```javascript
import { defineConfig } from 'astro/config';
import cloudflare from '@astrojs/cloudflare';


export default defineConfig({
  adapter: cloudflare(),
  build: {
    client: './',
    server: './_worker.js',
  },
});

```

--------------------------------

### Create Function to Fetch Published Articles from Drupal

Source: https://v6.docs.astro.build/en/guides/cms/drupal

Implements the `getArticles` asynchronous function to retrieve all published articles from Drupal. It utilizes `DrupalJsonApiParams` to construct the API query for article nodes and then uses `fetchUrl` to get and deserialize the data.

```typescript
import {Jsona} from "jsona";
import {DrupalJsonApiParams} from "drupal-jsonapi-params";
import type {DrupalNode} from "../types.ts";
import type {TJsonApiBody} from "jsona/lib/JsonaTypes";


// Get the Drupal Base Url.
export const baseUrl: string = import.meta.env.DRUPAL_BASE_URL;


/**
 * Fetch url from Drupal.
 *
 * @param url
 *
 * @return Promise<TJsonaModel | TJsonaModel[]> as Promise<any>
 */
export const fetchUrl = async (url: string): Promise<any> => {
    const request: Response = await fetch(url);
    const json: string | TJsonApiBody = await request.json();
    const dataFormatter: Jsona = new Jsona();
    return dataFormatter.deserialize(json);
}


/**
 * Get all published articles.
 *
 * @return Promise<DrupalNode[]>
 */
export const getArticles = async (): Promise<DrupalNode[]> => {
    const params: DrupalJsonApiParams = new DrupalJsonApiParams();
    params
        .addFields("node--article", [
            "title",
            "path",
            "body",
            "created",
        ])
        .addFilter("status", "1");
    const path: string = params.getQueryString();
    return await fetchUrl(baseUrl + '/jsonapi/node/article?' + path);
}
```

--------------------------------

### Storyblok BlogPost Component in Astro

Source: https://v6.docs.astro.build/en/guides/cms/storyblok

Renders title, description, and content from a blogPost Blok. Transforms rich text content to HTML using renderRichText. Includes storyblokEditable for in-editor editing.

```astro
---
import { storyblokEditable, renderRichText } from '@storyblok/astro'
const { blok } = Astro.props
const content = renderRichText(blok.content)
---
<article {...storyblokEditable(blok)}>
  <h1>{blok.title}</h1>
  <p>{blok.description}</p>
  <Fragment set:html={content} />
</article>

```

--------------------------------

### markdown.shikiConfig Configuration

Source: https://v6.docs.astro.build/en/reference/configuration-reference

Customize the Shiki syntax highlighter for Markdown code blocks. You can configure themes, languages, and transformers to tailor the appearance and functionality of code highlighting.

```APIDOC
## markdown.shikiConfig

### Description

Allows full configuration of Shiki, the default syntax highlighter used in Astro Markdown. Options include theme selection, custom languages, and transformers.

### Type

`Partial<ShikiConfig>`

### Configuration Options

- **theme** (`string`): Choose from Shiki's built-in themes (e.g., 'dracula').
- **themes** (`object`): Provide an object with `light` and `dark` themes for dual-theme support.
- **defaultColor** (`boolean`): Disable default colors for dual themes (added in v4.12.0).
- **langs** (`Array<string>`): Add custom languages to be supported by Shiki.
- **langAlias** (`object`): Define aliases for language IDs (e.g., `cjs` to `javascript`).
- **wrap** (`boolean`): Enable word wrap to prevent horizontal scrolling in code blocks.
- **transformers** (`Array<any>`): Add custom Shiki transformers for extended functionality.

### Example Usage

```javascript
import { defineConfig } from 'astro/config';

export default defineConfig({
  markdown: {
    shikiConfig: {
      theme: 'dracula',
      themes: {
        light: 'github-light',
        dark: 'github-dark',
      },
      defaultColor: false,
      langs: [],
      langAlias: {
        cjs: "javascript"
      },
      wrap: true,
      transformers: [],
    },
  },
});
```
```

--------------------------------

### Customizing Heading IDs with Rehype Plugins in Astro

Source: https://v6.docs.astro.build/en/guides/markdown-content

Configures Astro to use custom rehype plugins for processing Markdown. This example shows how to include `rehypeHeadingIds` and another plugin that relies on heading IDs, ensuring proper ID generation and access.

```javascript
import { defineConfig } from 'astro/config';
import { rehypeHeadingIds } from '@astrojs/markdown-remark';
import { otherPluginThatReliesOnHeadingIDs } from 'some/plugin/source';


export default defineConfig({
  markdown: {
    rehypePlugins: [
      rehypeHeadingIds,
      otherPluginThatReliesOnHeadingIDs,
    ],
  },
});
```

--------------------------------

### renderToResponse()

Source: https://v6.docs.astro.build/en/reference/container-reference

Renders an Astro component and returns a Response object.

```APIDOC
## `renderToResponse()`

### Description
It renders a component, and it returns a `Response` object.
It also accepts an object as a second argument that can contain a number of options.

### Method
`renderToResponse(component: AstroComponentFactory, options?: ContainerRenderOptions) => Promise<Response>`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
import { experimental_AstroContainer } from "astro/container";
import Card from "../src/components/Card.astro";


const container = await experimental_AstroContainer.create();
const result = await container.renderToResponse(Card);
```

### Response
#### Success Response (200)
- **Response**: A Response object containing the rendered component.

#### Response Example
```javascript
// Response object representing the rendered component
```
```

--------------------------------

### Configure Prism Syntax Highlighting Extension

Source: https://v6.docs.astro.build/en/guides/integrations-guide/markdoc

Applies the Prism extension to the Markdoc configuration to enable syntax highlighting. This requires importing the `prism` function from `@astrojs/markdoc/prism` and adding it to the `extends` array in `defineMarkdocConfig`.

```javascript
import { defineMarkdocConfig } from '@astrojs/markdoc/config';
import prism from '@astrojs/markdoc/prism';


export default defineMarkdocConfig({
  extends: [prism()],
});

```

--------------------------------

### Complete Astro Page for Pokémon List

Source: https://v6.docs.astro.build/en/guides/migrate-to-astro/from-nuxtjs

This is the final Astro component for the Pokédex page. It integrates data fetching directly within the script section using `fetch()`, imports a Layout component, and renders the Pokémon list. It shows the complete conversion from the Nuxt.js example.

```astro
---
import Layout from '../layouts/layout.astro';


const res = await fetch("https://pokeapi.co/api/v2/pokemon?limit=151");
const resJson = await res.json();
const pokemons = resJson.results.map(pokemon => {
    const name = pokemon.name;
    // https://pokeapi.co/api/v2/pokemon/1/
    const url = pokemon.url;
    const id = url.split("/")[url.split("/").length - 2];
    return {
        name,
        url,
        id
    }
});
---


<Layout title="Pokedex: Generation 1">
  <ul class="plain-list pokeList">
      {pokemons.map((pokemon) => (
          <li class="pokemonListItem" key={pokemon.name}>
              <a class="pokemonContainer" href={`/pokemon/${pokemon.name}`}>
                  <p class="pokemonId">No. {pokemon.id}</p>
                  <img class="pokemonImage" src={`https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${pokemon.id}.png`} alt={`${pokemon.name} picture`}/>
                  <h2 class="pokemonName">{pokemon.name}</h2>
              </a>
          </li>
      ))}
  </ul>
</Layout>


<style>
.pokeList {
  display: grid;
  grid-template-columns: repeat( auto-fit, minmax(250px, 1fr) );
  gap: 1rem;
}


/* ... */
</style>
```

--------------------------------

### Seed Development Database with TypeScript

Source: https://v6.docs.astro.build/en/guides/astro-db

This snippet demonstrates how to seed your Astro development database with initial data. It imports the necessary `db` object and table definitions from `astro:db` and uses `db.insert` to add data to the `Comment` and `Author` tables. This file (`db/seed.ts`) is automatically re-run when the dev server starts.

```typescript
import { db, Comment, Author } from 'astro:db';


export default async function() {
  await db.insert(Author).values([
    { id: 1, name: "Kasim" },
    { id: 2, name: "Mina" },
  ]);


  await db.insert(Comment).values([
    { authorId: 1, body: 'Hope you like Astro DB!' },
    { authorId: 2, body: 'Enjoy!'},
  ])
}
```

--------------------------------

### Configure Astro Site URL with Trailing Slash

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v2

Example configuration in `astro.config.mjs` demonstrating how to correctly set the `site` property to include a trailing slash. Astro v2.0 requires the `site` value to be used exactly as provided, unlike v1.x which automatically added a trailing slash.

```javascript
import { defineConfig } from 'astro/config';


export default defineConfig({
  site: 'https://example.com',
  site: 'https://example.com/',
});
```

--------------------------------

### Configure includeFiles and excludeFiles with Glob Patterns in Astro Netlify Adapter

Source: https://v6.docs.astro.build/en/guides/integrations-guide/netlify

Both includeFiles and excludeFiles support glob patterns for matching multiple files, allowing for more flexible file inclusion and exclusion rules.

```javascript
import { defineConfig } from 'astro/config';
import netlify from '@astrojs/netlify';


export default defineConfig({
  adapter: netlify({
    includeFiles: [
      './data/**/*.json'
    ],
    excludeFiles: [
      './node_modules/package/**/*',
      './src/**/*.test.js'
    ]
  }),
});

```

--------------------------------

### TypeScript Environment Interface for Xata

Source: https://v6.docs.astro.build/en/guides/backend/xata

Defines TypeScript interfaces for IntelliSense and type safety of environment variables used with Xata. This improves developer experience by providing autocompletion and compile-time checks.

```typescript
interface ImportMetaEnv {
  readonly XATA_API_KEY: string;
  readonly XATA_BRANCH?: string;
}


interface ImportMeta {
  readonly env: ImportMetaEnv;
}
```

--------------------------------

### Get Set-Cookie Headers from Response (Static Method) in JavaScript

Source: https://v6.docs.astro.build/en/reference/adapter-reference

Similar to `app.setCookieHeaders()`, `App.getSetCookieFromResponse()` is a static method that returns a generator yielding individual cookie header values from a `Response` object. This can be called at any time to process cookies.

```javascript
for (const cookie of App.getSetCookieFromResponse(response)) {
  response.headers.append('Set-Cookie', cookie);
}
```

--------------------------------

### Conditionally Render Cart Flyout in Solid

Source: https://v6.docs.astro.build/en/recipes/sharing-state-islands

Demonstrates conditional rendering of a `CartFlyout` component in Solid.js based on the `isCartOpen` atom. It uses `useStore` to get the reactive value and renders the flyout when the store's value is true.

```typescript
import { useStore } from '@nanostores/solid';
import { isCartOpen } from '../cartStore';


export default function CartFlyout() {
  const $isCartOpen = useStore(isCartOpen);


  return $isCartOpen() ? <aside>...</aside> : null;
}

```

--------------------------------

### Enable Server-Side Secret Validation in Astro

Source: https://v6.docs.astro.build/en/reference/configuration-reference

Demonstrates how to enable server-side validation of secret environment variables in Astro by setting `validateSecrets` to `true` within the `env` configuration. This ensures all secrets are checked on server start, which is beneficial for CI/CD pipelines.

```javascript
import { defineConfig, envField } from "astro/config"


export default defineConfig({
  env: {
    schema: {
      // ...
    },
    validateSecrets: true
  }
})
```

--------------------------------

### Browser Support and Recommendations for Prefetching

Source: https://v6.docs.astro.build/en/guides/prefetch

Details browser support for Astro's prefetching mechanism, including differences between Chrome, Firefox, and Safari, and provides recommendations for ensuring cross-browser compatibility.

```APIDOC
## Browser Support and Recommendations for Prefetching

### Description
Astro's prefetching utilizes `<link rel="prefetch">` where supported, falling back to the `fetch()` API. Understanding browser-specific behaviors and implementing proper caching headers is crucial for consistent performance.

### Browser Support Details:

*   **Chrome:** Fully supports `<link rel="prefetch">` and `<script type="speculationrules">` (with `clientPrerender` experiment enabled).
*   **Firefox:** Supports `<link rel="prefetch">` but may error without explicit cache headers (`Cache-Control`, `Expires`). `ETag` headers can help re-use prefetched resources even after errors.
*   **Safari:** Does not support `<link rel="prefetch">`, relies on `fetch()` API, requiring cache headers (`Cache-Control`, `Expires`, `ETag`). `ETag` headers may not work in private windows.

### Recommendations:

*   **Implement Cache Headers:** Ensure `Cache-Control`, `Expires`, and `ETag` headers are correctly set for all pages, especially for dynamic or server-side rendered content.
*   **Static/Prerendered Pages:** `ETag` headers are often automatically handled by deployment platforms.
*   **Dynamic/SSR Pages:** Manually configure appropriate cache headers based on content.

### Method
N/A (Information only)

### Endpoint
N/A

### Parameters
N/A

### Request Example
N/A

### Response
#### Success Response (200)
N/A

#### Response Example
N/A
```

--------------------------------

### Configure Local Font Variants in Astro

Source: https://v6.docs.astro.build/en/reference/experimental-flags/fonts

Sets up local font files using the 'local' provider. Requires 'name', 'cssVariable', and 'variants'. Each variant needs 'weight', 'style', and 'src'.

```javascript
import { defineConfig } from "astro/config";


export default defineConfig({
    experimental: {
        fonts: [{
            provider: "local",
            name: "Custom",
            cssVariable: "--font-custom",
            variants: [
                {
                    weight: 400,
                    style: "normal",
                    src: ["./src/assets/fonts/custom-400.woff2"]
                },
                {
                    weight: 700,
                    style: "normal",
                    src: ["./src/assets/fonts/custom-700.woff2"]
                }
                // ...
            ]
        }]
    }
});
```

--------------------------------

### Get Static Paths for Translated Content (Astro Static)

Source: https://v6.docs.astro.build/en/recipes/i18n

This Astro JavaScript code demonstrates how to use `getStaticPaths` to generate static pages for translated content. It fetches blog entries, extracts language and slug from the ID, and maps them to route parameters.

```javascript
import {
  getCollection,
  render
} from 'astro:content';


export async function getStaticPaths() {
  const pages = await getCollection('blog');


  const paths = pages.map(page => {
    const [lang, ...slug] = page.id.split('/');
    return { params: { lang, slug: slug.join('/') || undefined }, props: page };
  });


  return paths;
}


const { lang, slug } = Astro.params;
const page = Astro.props;
const formattedDate = page.data.date.toLocaleString(lang);
const { Content } = await render(page);

```

--------------------------------

### Mapping ApostropheCMS Widgets to Astro Components (JavaScript)

Source: https://v6.docs.astro.build/en/guides/cms/apostrophecms

This JavaScript file maps ApostropheCMS widget types to their corresponding Astro components. It exports an object where keys are Apostrophe widget names and values are the imported Astro components.

```javascript
import RichTextWidget from './RichTextWidget.astro';
import ImageWidget from './ImageWidget.astro';


const widgetComponents = {
  '@apostrophecms/rich-text': RichTextWidget,
  '@apostrophecms/image': ImageWidget
};


export default widgetComponents;
```

--------------------------------

### Select all rows from Comment table in Astro DB

Source: https://v6.docs.astro.build/en/guides/astro-db

This example demonstrates how to select all rows from a 'Comment' table using Astro DB. It fetches all seeded development data, making it available for use in page templates. The result is an array of comment objects.

```astro
---
import { db, Comment } from 'astro:db';


const comments = await db.select().from(Comment);
---


<h2>Comments</h2>


<p>
  {
    comments.map(({ author, body }) => (
    <article>
      <p>Author: {author}</p>
      <p>{body}</p>
    </article>
  ))
  }
</p>

```

--------------------------------

### Define Cache Hint for Last Modified Date (JavaScript)

Source: https://v6.docs.astro.build/en/reference/content-loader-reference

This example shows how to define a cache hint for a single product using its last update date. The `lastModified` property can be used to set HTTP cache headers like `Last-Modified` and `If-Modified-Since`, improving cache efficiency.

```javascript
return {
  /* ... */
  cacheHint: {
    lastModified: new Date(product.updatedAt)
  },
};
```

--------------------------------

### Use Custom AstroGreet Component with Different Messages

Source: https://v6.docs.astro.build/en/guides/client-side-scripts

This example shows how to use the custom `AstroGreet` component multiple times within an Astro page. It demonstrates passing different `message` props to each instance, allowing for personalized greetings. The component utilizes the `data-*` attribute mechanism to pass these props to its client-side script.

```html
---
import AstroGreet from '../components/AstroGreet.astro';
---


<!-- Use the default message: “Welcome, world!” -->
<AstroGreet />


<!-- Use custom messages passed as a props. -->
<AstroGreet message="Lovely day to build components!" />
<AstroGreet message="Glad you made it! 👋" />
```

--------------------------------

### Create Better Auth Client for Solid

Source: https://v6.docs.astro.build/en/guides/authentication

This code snippet initializes a Better Auth client for SolidJS applications. It uses the `createAuthClient` helper from the 'better-auth/solid' module and exports the client instance along with authentication functions.

```typescript
import { createAuthClient } from 'better-auth/solid';


export const authClient = createAuthClient();


export const {signIn, signOut } = authClient;

```

--------------------------------

### Import Global Stylesheet in Astro Page

Source: https://v6.docs.astro.build/en/tutorial/2-pages/5

This Astro frontmatter snippet shows a minimal example of importing a global CSS file into an Astro page. It's used to apply site-wide styles to specific pages like `index.astro` or `blog.astro`.

```astro
---
import '../styles/global.css';
---

```

--------------------------------

### Declare Associated Image in Content Collection Frontmatter (Astro)

Source: https://v6.docs.astro.build/en/guides/images

This example demonstrates how to associate an image with a content collection entry, like a blog post's cover image, directly within the frontmatter. The image path is relative to the current folder, and an `alt` attribute is included for accessibility.

```markdown
---
title: "My first blog post"
cover: "./firstpostcover.jpeg" # will resolve to "src/content/blog/firstblogcover.jpeg"
coverAlt: "A photograph of a sunset behind a mountain range."
---


This is a blog post

```

--------------------------------

### Generate basic RSS feed with @astrojs/rss

Source: https://v6.docs.astro.build/en/recipes/rss

Create an RSS feed by importing the `rss()` helper from '@astrojs/rss' and exporting a GET function in a `.xml.js` file. This function takes configuration options like title, description, site, and items.

```javascript
import rss from '@astrojs/rss';


export function GET(context) {
  return rss({
    // `<title>` field in output xml
    title: 'Buzz’s Blog',
    // `<description>` field in output xml
    description: 'A humble Astronaut’s guide to the stars',
    // Pull in your project "site" from the endpoint context
    // https://docs.astro.build/en/reference/api-reference/#site
    site: context.site,
    // Array of `<item>`s in output xml
    // See "Generating items" section for examples using content collections and glob imports
    items: [],
    // (optional) inject custom xml
    customData: `<language>en-us</language>`,
  });
}
```

--------------------------------

### Build and Push Docker Image for Google Cloud Deployment

Source: https://v6.docs.astro.build/en/guides/deploy/google-cloud

Commands to build a Docker container image locally, tag it for a registry, and push it to a Google Cloud Artifact Registry or other compatible registry. This is a prerequisite for deploying Astro sites to Cloud Run.

```bash
# build your container
docker build .

docker tag SOURCE_IMAGE HOSTNAME/PROJECT-ID/TARGET-IMAGE:TAG

# Push your image to a registry
docker push HOSTNAME/PROJECT-ID/IMAGE:TAG
```

--------------------------------

### Register Blog Modules in ApostropheCMS App (JavaScript)

Source: https://v6.docs.astro.build/en/guides/cms/apostrophecms

This JavaScript snippet shows how to register the newly created 'blog' piece and 'blog-page' modules within the main ApostropheCMS application configuration (`app.js`). This makes the modules available for use in the project.

```javascript
require('apostrophe')({
  // other configuration options
  modules: {
    // other project modules
    blog: {},
    'blog-page': {}
  }
});

```

--------------------------------

### Serve Image Response with Custom Headers - Astro API

Source: https://v6.docs.astro.build/en/guides/endpoints

This example shows how to create an Astro API route that serves an image with specific headers. It fetches an image from a URL and returns it as a PNG, setting the 'Content-Type' header to 'image/png' using the `Response` object.

```javascript
export async function GET({ params, request }) {
  const response = await fetch(
    "https://docs.astro.build/assets/full-logo-light.png",
  );
  const buffer = Buffer.from(await response.arrayBuffer());


  return new Response(buffer, {
    headers: { "Content-Type": "image/png" },
  });
}
```

--------------------------------

### Astro Middleware for HTML Redaction (JavaScript/TypeScript)

Source: https://v6.docs.astro.build/en/guides/middleware

An example of an asynchronous `onRequest` middleware function that modifies the response body. It fetches the response text, replaces a specific string ('PRIVATE INFO') with 'REDACTED', and returns a new Response with the modified HTML.

```javascript
export const onRequest = async (context, next) => {
    const response = await next();
    const html = await response.text();
    const redactedHtml = html.replaceAll("PRIVATE INFO", "REDACTED");


    return new Response(redactedHtml, {
        status: 200,
        headers: response.headers
    });
};
```

--------------------------------

### astro db push

Source: https://v6.docs.astro.build/en/guides/integrations-guide/db

Safely push database configuration changes to your project database. This command checks for potential data loss and guides migration steps. Use `--force-reset` to reset all production data if a breaking schema change is required.

```APIDOC
## `astro db push`

### Description
Safely push database configuration changes to your project database. This command checks for potential data loss and guides migration steps. Use `--force-reset` to reset all production data if a breaking schema change is required.

### Method
CLI Command

### Endpoint
N/A

### Parameters
#### Flags
- **`--force-reset`** (boolean) - Optional - Reset all production data if a breaking schema change is required.

### Request Example
```bash
astro db push
astro db push --force-reset
```

### Response
#### Success Response
Database configuration pushed successfully.

#### Response Example
```
Database schema pushed successfully.
```
```

--------------------------------

### Render Live Collection Content in Astro

Source: https://v6.docs.astro.build/en/guides/content-collections

Demonstrates how to render content from live collections in Astro when the loader returns a `rendered` property. It utilizes the `render()` function and `<Content />` component, and includes error handling for cases where content cannot be retrieved.

```typescript
---
export const prerender = false; // Not needed in 'server' mode


import { getLiveEntry, render } from 'astro:content';
const { entry, error } = await getLiveEntry('articles', Astro.params.id);
if (error) {
  return Astro.rewrite('/404');
}


const { Content } = await render(entry);
---


<h1>{entry.data.title}</h1>
<Content />

```

--------------------------------

### Incorrect Astro Component Rendering Syntax

Source: https://v6.docs.astro.build/en/reference/errors/invalid-component-args

Illustrates the incorrect method of rendering Astro components by calling them as functions. This approach leads to 'Invalid component arguments' errors. The examples highlight common mistakes that developers might make.

```javascript
// Incorrect: Calling component as a function
Component()

// Incorrect: Mapping and calling component as a function
{items.map(Component)}
```

--------------------------------

### Import Zod from astro/zod (Astro)

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v6

Demonstrates the recommended way to import Zod in Astro projects to ensure compatibility with the version Astro uses internally.

```typescript
import { z } from 'astro/zod';
```

--------------------------------

### Astro Integration for Dev Toolbar App

Source: https://v6.docs.astro.build/en/recipes/making-toolbar-apps

This TypeScript code defines an Astro integration that adds a custom dev toolbar app. It uses the `astro:config:setup` hook and the `addDevToolbarApp` function to register the app with its ID, name, icon, and entrypoint.

```typescript
import {
  fileURLToPath
} from 'node:url';
import type { AstroIntegration } from 'astro';


export default {
  name: 'my-astro-integration',
  hooks: {
    'astro:config:setup': ({ addDevToolbarApp }) => {
      addDevToolbarApp({
        id: "my-toolbar-app",
        name: "My Toolbar App",
        icon: "🚀",
        entrypoint: fileURLToPath(new URL('./app.ts', import.meta.url))
      });
    },
  },
} satisfies AstroIntegration;
```

--------------------------------

### Importing Wasm Module in Astro for Cloudflare

Source: https://v6.docs.astro.build/en/guides/integrations-guide/cloudflare

Shows how to import and use a WebAssembly (.wasm) module within an Astro server-side route for Cloudflare Workers. The Wasm module is instantiated and its exported functions can be called to perform computationally intensive tasks. This example imports `add.wasm` and uses its `add` function.

```javascript
// Import the WebAssembly module
import mod from '../util/add.wasm';


// Instantiate first in order to use it
const addModule: any = new WebAssembly.Instance(mod);


export async function GET(context) {
  const a = Number.parseInt(context.params.a);
  const b = Number.parseInt(context.params.b);
  return new Response(`${addModule.exports.add(a, b)}`);
}

```

--------------------------------

### Generate Individual Blog Post Pages from Collection (Astro)

Source: https://v6.docs.astro.build/en/tutorial/6-islands/4

This snippet demonstrates how to create dynamic pages for each blog post within an Astro content collection. It uses `getCollection()` to fetch posts and `render()` to process their content, making slugs and page content available to each generated page. This replaces the need for individual Markdown files to automatically become pages.

```astro
---
import { getCollection, render } from 'astro:content';


export async function getStaticPaths() {
  const posts = await getCollection('blog');
  return posts.map(post => ({
    params: { slug: post.id }, props: { post },
  }));
}


const { post } = Astro.props;
const { Content } = await render(post);
---
```

--------------------------------

### Implement an Astro API Endpoint for Image Service

Source: https://v6.docs.astro.build/en/reference/image-service-reference

This example shows how to create an Astro API route that utilizes a custom image service. It uses `getConfiguredImageService` and `imageConfig` to parse the request URL, transform the image, and return the processed image data with the correct content type.

```typescript
import type { APIRoute } from "astro";
import { getConfiguredImageService, imageConfig } from 'astro:assets';


export const GET: APIRoute = async ({ request }) => {
  const imageService = await getConfiguredImageService();


  const imageTransform = imageService.parseURL(new URL(request.url), imageConfig);
  // ... fetch the image from imageTransform.src and store it in inputBuffer
  const { data, format } = await imageService.transform(inputBuffer, imageTransform, imageConfig);
  return new Response(data, {
      status: 200,
      headers: {
        'Content-Type': mime.getType(format) || ''
      }
    }
  );
}

```

--------------------------------

### Add Type Declarations for YAML Imports in Astro

Source: https://v6.docs.astro.build/en/recipes/add-yaml-support

Provides a TypeScript declaration file (`*.d.ts`) to enable editor type hints for imported YAML data. This improves developer experience by providing autocompletion and type checking for YAML content.

```typescript
// Specify the file extension you want to import
declare module "*.yml" {
  const value: any; // Add type definitions here if desired
  export default value;
}
```

--------------------------------

### Replace ASSETS_PREFIX with astro:config/server build.assetsPrefix

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v6

Shows how to replace the deprecated `import.meta.env.ASSETS_PREFIX` with the `build.assetsPrefix` property imported from `astro:config/server`. This is a direct replacement for accessing the `build.assetsPrefix` configuration value in Astro v6, providing a more direct and type-safe method compared to the environment variable.

```javascript
import { someLogic } from "./utils"
import { build } from "astro:config/server"


someLogic(import.meta.env.ASSETS_PREFIX)
someLogic(build.assetsPrefix)
```

--------------------------------

### Import Local Stylesheet in Astro

Source: https://v6.docs.astro.build/en/guides/styling

Demonstrates how to import a local CSS file (e.g., `../styles/utils.css`) directly into an Astro component's frontmatter using ESM import syntax. Astro automatically bundles and optimizes these imported stylesheets, and this method also supports CSS preprocessor files.

```astro
---
// Astro will bundle and optimize this CSS for you automatically
// This also works for preprocessor files like .scss, .styl, etc.
import '../styles/utils.css';
---
<html><!-- Your page here --></html>
```

--------------------------------

### Astro Script Tag Behavior Change (v0.25+)

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v1

Demonstrates the change in default behavior for Astro script tags. Previously, 'hoist' was an attribute, but now it's the default. The 'is:inline' directive can be used to revert to the old behavior.

```astro
// v0.25
<script hoist type="module">
// v0.26+
<script>
```

--------------------------------

### Rewrite on HTTP Status Code

Source: https://v6.docs.astro.build/en/guides/routing

Conditionally rewrites the response based on the HTTP status code. This example uses an `onRequest` middleware to rewrite to the root path if the initial response status is 404. This allows custom handling for errors or missing pages.

```javascript
export const onRequest = async (context, next) => {
  const response = await next();
  if (response.status === 404) {
    return context.rewrite("/");
  }
  return response;
}
```

--------------------------------

### Create New Astro Project with npm, pnpm, or Yarn

Source: https://v6.docs.astro.build/en/guides/migrate-to-astro/from-create-react-app

Provides commands to initialize a new Astro project using different package managers. This is the first step in setting up an Astro environment to integrate your CRA application.

```bash
npm create astro@latest

```

```bash
pnpm create astro@latest

```

```bash
yarn create astro@latest

```

--------------------------------

### Preserve Inline Script Behavior with `is:inline` in Astro

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v5

This example shows how to maintain the previous behavior of conditionally rendered scripts in Astro v5.0 by explicitly adding the `is:inline` attribute. In v5.0, conditionally rendered scripts are no longer implicitly inlined by default.

```astro
---
type Props = {
  showAlert: boolean
}

const { showAlert } = Astro.props;
---
{
  showAlert && <script is:inline>alert("Some very important code!!")</script>
}
```

--------------------------------

### Calling an Action from Client-Side JavaScript

Source: https://v6.docs.astro.build/en/guides/actions

Demonstrates how to import and call an Astro Action from a client-side script.

```APIDOC
## Client-Side Action Call

### Description
This code snippet shows how to import the `actions` object and call a defined action (`getGreeting`) from client-side JavaScript.

### Method
N/A (Client-side JavaScript)

### Endpoint
N/A (Calls the internal `/actions` endpoint)

### Parameters
#### Action Input
- **name** (string) - Required - The name to pass to the `getGreeting` action.

### Request Example
```javascript
import { actions } from 'astro:actions';

const button = document.querySelector('button');
button?.addEventListener('click', async () => {
  const { data, error } = await actions.getGreeting({ name: "Houston" });
  if (!error) {
    alert(data);
  }
});
```

### Response
#### Action Result
- **data** (string) - The greeting string returned by the action.
- **error** (object) - An error object if the action call failed.

#### Response Example (Success)
```javascript
// If action returns "Hello, Houston!"
alert("Hello, Houston!");
```
```

--------------------------------

### Define a generic collection query function with CollectionKey

Source: https://v6.docs.astro.build/en/reference/modules/astro-content

This example shows how to use the `CollectionKey` type to create a generic function that queries any Astro content collection. The `queryCollection` function accepts a `CollectionKey` and uses `getCollection` to retrieve entries, filtering out drafts.

```typescript
import { type CollectionKey, getCollection } from 'astro:content';


export async function queryCollection(collection: CollectionKey) {
  return getCollection(collection, ({ data }) => {
    return data.draft !== true;
  });
}
```

--------------------------------

### Push Application to Zerops

Source: https://v6.docs.astro.build/en/guides/deploy/zerops

Triggers the deployment of your application to Zerops. This command should be run from the root directory of your project where the 'zerops.yml' file is located.

```bash
zcli push
```

--------------------------------

### Astro Component for Image Widget with Placeholders (Astro)

Source: https://v6.docs.astro.build/en/guides/cms/apostrophecms

This Astro component handles image widgets, including fallback and placeholder logic. It conditionally sets the image source based on widget properties or a fallback, allowing for on-page editing.

```astro
---
const { widget } = Astro.props;
const placeholder = widget?.aposPlaceholder;
const src = placeholder ?
  '/images/image-widget-placeholder.jpg' :
  widget?._image[0]?.attachment?._urls['full'];
---
<style>
  .img-widget {
    width: 100%;
  }
</style>
<img class="img-widget" {src} />
```

--------------------------------

### Apply Custom Local Font to HTML Element

Source: https://v6.docs.astro.build/en/guides/fonts

Applies a custom font defined via @font-face to an HTML element using CSS. This example targets an h1 tag with the 'DistantGalaxy' font.

```html
---
---


<h1>In a galaxy far, far away...</h1>


<p>Custom fonts make my headings much cooler!</p>


<style>
h1 {
  font-family: 'DistantGalaxy', sans-serif;
}
</style>
```

--------------------------------

### Build Astro Site Programmatically

Source: https://v6.docs.astro.build/en/reference/programmatic-reference

The `build()` function programmatically builds your Astro site for deployment, mirroring the `astro build` command. It accepts an `AstroInlineConfig` object and optional `BuildOptions`.

```javascript
import { build } from "astro";


await build({
  root: "./my-project",
});
```

--------------------------------

### Using URL

Source: https://v6.docs.astro.build/en/reference/api-reference

Details how to use the `url` object to interact with the current request URL.

```APIDOC
## Using URL

### Description
The `url` property provides a `URL` object constructed from the current `request.url`. This is useful for accessing properties like `pathname` and `origin`.

### Example 1: Accessing URL Properties
```astro
<h1>The current URL is: {Astro.url}</h1>
<h1>The current URL pathname is: {Astro.url.pathname}</h1>
<h1>The current URL origin is: {Astro.url.origin}</h1>
```

### Example 2: Constructing New URLs
```astro
---
// Example: Construct a canonical URL using your production domain
const canonicalURL = new URL(Astro.url.pathname, Astro.site);
// Example: Construct a URL for SEO meta tags using your current domain
const socialImageURL = new URL('/images/preview.png', Astro.url);
---
<link rel="canonical" href={canonicalURL} />
<meta property="og:image" content={socialImageURL} />
```
```

--------------------------------

### Query Neon Database from Astro Component

Source: https://v6.docs.astro.build/en/guides/backend/neon

Demonstrates how to query the Neon database from an Astro component. It fetches the current time from the database using the initialized Neon client and displays it on the page.

```astro
---
import { sql } from '../lib/neon';


const response =  await  sql`SELECT NOW() as current_time`;
const currentTime = response[0].current_time;
---


<h1>Current Time</h1>
<p>The time is: {currentTime}</p>
```

--------------------------------

### Article Page Template with Content Rendering (Astro)

Source: https://v6.docs.astro.build/en/guides/cms/strapi

Astro component template for displaying individual article content. It includes the `getStaticPaths` function to fetch article data dynamically. The template renders the article's title, image, content (as plain text, markdown, or HTML), and uses the `STRAPI_URL` environment variable for image sources.

```astro
---
import fetchApi from '../../lib/strapi';
import type Article from '../../interfaces/article';


export async function getStaticPaths() {
  const articles = await fetchApi<Article[]>({
    endpoint: 'articles',
    wrappedByKey: 'data',
  });


  return articles.map((article) => ({
    params: { slug: article.slug },
    props: article,
  }));
}
type Props = Article;


const article = Astro.props;
---


<!DOCTYPE html>
<html lang="en">
  <head>
    <title>{article.title}</title>
  </head>


  <body>
    <main>
      <img src={import.meta.env.STRAPI_URL + article.image.data.url} />


      <h1>{article.title}</h1>


      <!-- Render plain text -->
      <p>{article.content}</p>
      <!-- Render markdown -->
      <MyMarkdownComponent>
        {article.content}
      </MyMarkdownComponent>
      <!-- Render html -->
      <Fragment set:html={article.content} />
    </main>
  </body>
</html>
```

--------------------------------

### Fetch and Display Caisy Content in Astro

Source: https://v6.docs.astro.build/en/guides/cms/caisy

This snippet demonstrates how to initialize a GraphQL client with Caisy API credentials, fetch blog article data based on a slug, and render the fetched content, including rich text, on an Astro page. It requires the `graphql-request` library and the `@caisy/rich-text-astro-renderer` package.

```astro
import RichTextRenderer from '@caisy/rich-text-astro-renderer';
import { gql, GraphQLClient } from 'graphql-request';


const params = Astro.params;


const client = new GraphQLClient(
  `https://cloud.caisy.io/api/v3/e/${import.meta.env.CAISY_PROJECT_ID}/graphql`,
  {
    headers: {
      'x-caisy-apikey': import.meta.env.CAISY_API_KEY
    }
  }
);
const gqlResponse = await client.request(
  gql`
    query allBlogArticle($slug: String) {
      allBlogArticle(where: { slug: { eq: $slug } }) {
        edges {
          node {
            text {
              json
            }
            title
            slug
            id
          }
        }
      }
    }
  `,
  { slug: params.slug }
);


const post = gqlResponse?.allBlogArticle?.edges?.[0]?.node;

```

```html
<h1>{post.title}</h1>
<RichTextRenderer node={post.text.json} />

```

--------------------------------

### Initialize Neon Client in Astro

Source: https://v6.docs.astro.build/en/guides/backend/neon

Initializes the Neon database client using the connection URL from environment variables. This client instance is then used to execute queries against the Neon database.

```typescript
import { neon } from '@neondatabase/serverless';


export const sql = neon(import.meta.env.NEON_DATABASE_URL);
```

--------------------------------

### Import Stylesheet from npm Package (with extension)

Source: https://v6.docs.astro.build/en/guides/styling

Shows how to import a CSS file from an npm package when the package recommends using the file extension in the import path (e.g., `package-name/styles.css`). This import works like a local stylesheet and is bundled and optimized by Astro.

```astro
---
import 'package-name/styles.css';
---
<html><!-- Your page here --></html>
```

--------------------------------

### Get path by locale code with Astro i18n

Source: https://v6.docs.astro.build/en/reference/modules/astro-i18n

Retrieves the custom path segment configured for a given locale code. This is useful when you have defined specific path aliases for locales in your Astro configuration.

```javascript
export default defineConfig({
  i18n: {
    locales: ["es", "en", {
      path: "french",
      codes: ["fr", "fr-BR", "fr-CA"]
    }]
  }
})
```

```javascript
import { getPathByLocale } from 'astro:i18n';

getPathByLocale("fr"); // returns "french"
getPathByLocale("fr-CA"); // returns "french"
```

--------------------------------

### Apply CSS Class to Astro <Image /> Component

Source: https://v6.docs.astro.build/en/guides/images

Shows how to apply a CSS class to the Astro `<Image />` component. The provided class is directly applied to the generated `<img>` element, allowing for styling of the optimized image. This example also includes the mandatory `alt` attribute.

```astro
---
import { Image } from 'astro:assets';
import myImage from '../assets/my_image.png';
---


<!-- `alt` is mandatory on the Image component -->
<Image src={myImage} alt="" class="my-class" />

```

```html
<!-- Prerendered output -->
<img
  src="/_astro/my_image.hash.webp"
  width="1600"
  height="900"
  decoding="async"
  loading="lazy"
  class="my-class"
  alt=""
/>

```

--------------------------------

### Get relative locale URL list with Astro i18n

Source: https://v6.docs.astro.build/en/reference/modules/astro-i18n

Returns an array of relative URLs for all configured locales for a given path. This function is useful for generating links to the same page in different languages.

```javascript
import { getRelativeLocaleUrlList } from 'astro:i18n';

// Example usage (assuming multiple locales are configured)
// const urls = getRelativeLocaleUrlList("about");
// console.log(urls); // Output might be: ["/en/about", "/fr/about", "/es/about"]
```

--------------------------------

### Map Contentful Entries to Page Params and Props (Astro/TypeScript)

Source: https://v6.docs.astro.build/en/guides/cms/contentful

This code extends the `getStaticPaths()` function to map fetched Contentful blog post entries into page-specific parameters and props. It extracts the slug for routing and formats title, content (converted to HTML), and date for the page.

```astro
---
import { contentfulClient } from "../../lib/contentful";
import { documentToHtmlString } from "@contentful/rich-text-html-renderer";
import type { BlogPost } from "../../lib/contentful";


export async function getStaticPaths() {
  const entries = await contentfulClient.getEntries<BlogPost>({
    content_type: "blogPost",
  });


  const pages = entries.items.map((item) => ({
    params: { slug: item.fields.slug },
    props: {
      title: item.fields.title,
      content: documentToHtmlString(item.fields.content),
      date: new Date(item.fields.date).toLocaleDateString(),
    },
  }));
  return pages;
}
---

```

--------------------------------

### Use Uppercase HTTP Method Names (Astro)

Source: https://v6.docs.astro.build/en/guides/upgrade-to/v4

Astro v4.0 requires HTTP request method names to be in uppercase. Deprecated lowercase names (`get`, `post`, `put`, `all`, `del`) are no longer supported.

--------------------------------

### Render Individual Blog Post in Astro

Source: https://v6.docs.astro.build/en/guides/cms/kontent-ai

Provides the HTML template for an individual blog post page in Astro using SSG. It receives blog post data via `Astro.props.blogPost` and displays the title, teaser, content, and date. The teaser and content are rendered as HTML fragments.

```astro
---
import { deliveryClient } from '../../lib/kontent';
import type { BlogPost } from '../../models';
import { contentTypes } from '../../models/project/contentTypes';


export async function getStaticPaths() {
    const blogPosts = await deliveryClient
        .items<BlogPost>()
        .type(contentTypes.blog_post.codename)
        .toPromise()


    return blogPosts.data.items.map(blogPost => ({
        params: { slug: blogPost.elements.url_slug.value },
        props: { blogPost }
    }))
}


const blogPost: BlogPost = Astro.props.blogPost
---
<html lang="en">
    <head>
        <meta charset="utf-8" />
        <meta name="viewport" content="width=device-width" />
        <title>{blogPost.elements.title.value}</title>
    </head>
    <body>
        <article>
            <h1>{blogPost.elements.title.value}</h1>
            <Fragment set:html={blogPost.elements.teaser.value} />
            <Fragment set:html={blogPost.elements.content.value} />
            <time>{new Date(blogPost.elements.date.value ?? "")}</time>
    </body>
</html>
```

--------------------------------

### Navigation Component with Translated Paths (Astro/TypeScript)

Source: https://v6.docs.astro.build/en/recipes/i18n

This Astro component example shows how to use the `useTranslatedPath` helper function to generate navigation links. It dynamically creates links based on the current language and predefined translations, ensuring that navigation is consistent across different language versions of the site.

```astro
---
import { getLangFromUrl, useTranslations, useTranslatedPath } from '../i18n/utils';


const lang = getLangFromUrl(Astro.url);
const t = useTranslations(lang);
const translatePath = useTranslatedPath(lang);
---
<ul>
    <li>
        <a href={translatePath('/home/')}>
          {t('nav.home')}
        </a>
    </li>
    <li>
        <a href={translatePath('/about/')}>
          {t('nav.about')}
        </a>
    </li>
    <li>
        <a href="https://twitter.com/astrodotbuild">
          {t('nav.twitter')}
        </a>
    </li>
</ul>

```