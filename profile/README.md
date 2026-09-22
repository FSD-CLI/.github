<!--
  FSD CLI · GitHub organization profile
  Destination: FSD-CLI/.github → profile/README.md
  Content checked against the public CLI README, template registry,
  inspection implementation, and npm package metadata on 2026-09-22.
  Keep framework availability aligned with bin/core/template-registry.mjs.
-->

<div align="center">

<h1>FSD CLI</h1>

<h3>Architecture from day one.</h3>

<p>
  Start with a clear structure. Keep building with the same conventions.<br />
  Frontend scaffolding and generators built around <b>Feature-Sliced Design</b>.
</p>

<p>
  <a href="https://www.npmjs.com/package/create-fsd-architecture"><img src="https://img.shields.io/npm/v/create-fsd-architecture?style=flat-square&amp;label=npm&amp;color=6366f1" alt="Latest npm version" /></a>
  <a href="https://www.npmjs.com/package/create-fsd-architecture"><img src="https://img.shields.io/npm/dm/create-fsd-architecture?style=flat-square&amp;label=downloads%2Fmonth&amp;color=6366f1" alt="Monthly npm downloads" /></a>
  <a href="https://github.com/FSD-CLI/cli"><img src="https://img.shields.io/github/stars/FSD-CLI/cli?style=flat-square&amp;label=GitHub%20stars&amp;color=6366f1" alt="GitHub stars" /></a>
  <a href="https://github.com/FSD-CLI/cli/blob/main/LICENSE"><img src="https://img.shields.io/github/license/FSD-CLI/cli?style=flat-square&amp;color=6366f1" alt="CLI license" /></a>
</p>

<p>
  <a href="https://fsd-docs.vercel.app"><b>Documentation</b></a>
  &nbsp; · &nbsp;
  <a href="#start-building"><b>Quick start</b></a>
  &nbsp; · &nbsp;
  <a href="#explore-the-ecosystem"><b>Repositories</b></a>
  &nbsp; · &nbsp;
  <a href="https://github.com/FSD-CLI/cli/issues"><b>Feedback</b></a>
</p>

<p><sub>React + Vite &nbsp; / &nbsp; Next.js &nbsp; / &nbsp; Vue + Vite &nbsp; / &nbsp; Nuxt &nbsp; / &nbsp; SvelteKit</sub></p>

</div>

Give your next feature a place to belong

As a frontend grows, every new feature brings another decision: where should its UI, state, and API code live?

FSD CLI helps you establish that structure at the start. Choose your framework and stack, scaffold an FSD project, and generate new slices using the configuration you already selected.

This organization brings together the CLI and its framework templates.

Start with a foundation

Continue with consistency

Inspect the setup

Select your framework, API client, state, forms, and package manager through an interactive setup.

Generate features, entities, widgets, and pages using your saved project configuration.

Check configuration and layer directories, inspect the local toolchain, and print the active configuration.

Start building

npx create-fsd-architecture@latest my-app

Follow the prompts to choose your stack, install dependencies, and optionally start the development server.

Requirements: Node.js 20+ for the CLI. Generated Nuxt and SvelteKit projects require Node.js 22.22.2+ according to the current CLI documentation; check your selected template's requirements before starting.

<details>
<summary><b>Prefer a repeatable, non-interactive setup?</b></summary>

Specify the framework and package manager explicitly. This example creates the project without installing dependencies or starting the development server:

npx create-fsd-architecture@latest my-app \
  --framework react-vite \
  --package-manager pnpm \
  --yes \
  --no-install \
  --no-start

Explore the available options and templates:

npx create-fsd-architecture@latest --help
npx create-fsd-architecture@latest --list-templates

</details>

Explore the ecosystem

One CLI, with templates and integrations tailored to each framework.

Project

Purpose

Explore

create-fsd-architecture

Interactive setup, project generation, slice generators, and inspection commands.

Source · npm

React + Vite

React template with a complete FSD structure.

FSD

Next.js

Next.js App Router template.

FSD-NEXTJS

Vue + Vite

Vue template with framework-native FSD segments.

fsd-vue

Nuxt

Nuxt template with framework-native FSD segments.

fsd-nuxt

SvelteKit

SvelteKit template with framework-native FSD segments.

fsd-sveltekit

<details>
<summary><b>Framework IDs for scripts and automation</b></summary>

Framework

CLI ID

Registry status

React + Vite

react-vite

Stable

Next.js

nextjs

Stable

Vue + Vite

vue-vite

Stable

Nuxt

nuxt

Stable

SvelteKit

sveltekit

Stable

The organization also contains fsd-angular. It is not currently listed as an available template in the CLI registry.

</details>

A structure you can build on

The generated architecture separates application setup, page composition, user interactions, business entities, and shared foundations.

Layer

Responsibility

Example

app

Application setup, providers, routing integration, and global styles.

Query provider, app initialization

pages

Page-level compositions.

Product details page

widgets

Larger self-contained interface blocks.

Site header, dashboard overview

features

User interactions and business actions.

Add to cart, sign in

entities

Business concepts and their representations.

Product, user, order

shared

Reusable foundations and infrastructure.

UI primitives, API client, utilities

Source roots and route integration follow each framework's conventions. For example, Nuxt places FSD layers under app/, while SvelteKit keeps thin route wrappers in src/routes.

Learn about the methodology in the Feature-Sliced Design documentation, and see the CLI documentation for template-specific behavior.

Choose once. Generate consistently.

Your setup choices are stored in fsd.config.json. Generators read that configuration to use the stack already selected for the project.

Run these commands from the generated project's root:

# Preview a new feature without writing files
npx create-fsd-architecture@latest --generate feature auth --dry-run

# Generate the feature
npx create-fsd-architecture@latest --generate feature auth

# Add an entity or a page
npx create-fsd-architecture@latest --generate entity product
npx create-fsd-architecture@latest --generate page settings

Available generator types: feature · entity · widget · page.

Existing slices are protected by default. Page generation includes framework-specific route integration.

<details>
<summary><b>What gets remembered in the project configuration?</b></summary>

Framework and package manager.

API client.

Server-state and client-state choices.

Forms integration.

UI configuration.

Available combinations depend on the selected framework. The CLI uses a capability matrix to validate supported combinations.

To view the active configuration:

npx create-fsd-architecture@latest config

</details>

Inspect your project setup

Command

What it checks or displays

npx create-fsd-architecture@latest check

Loads the FSD configuration and checks for package.json and the required layer directories.

npx create-fsd-architecture@latest doctor

Runs the project checks and checks Node.js, Git, and the configured package manager.

npx create-fsd-architecture@latest config

Prints the loaded project configuration as JSON.

These commands inspect project setup; they do not currently analyze source-code import boundaries.

Built for framework-specific behavior

The CLI shares project lifecycle and generation infrastructure while keeping framework-specific behavior behind adapters.

Building block

Role

Template registry

Template identity, repository mapping, and availability.

Capability matrix

Supported stack combinations for each framework.

Framework adapters

Framework-specific integration behavior.

Project lifecycle

Project creation, configuration, and installation workflow.

Generators

Reusable building blocks for new slices.

Browse the implementation to explore how these pieces fit together.

Build with us

Found an issue, have an idea, or want to improve a template? Contributions can start with a reproducible bug report, a documentation improvement, or a focused pull request.

I want to…

Start here

Learn how to use the CLI

Read the documentation

Report a CLI bug or suggest an improvement

Open an issue

Improve a framework template

Open the relevant repository in the ecosystem table above.

Contribute to the CLI

Review existing pull requests and the source.

Follow project changes

Read the changelog · View releases

<details>
<summary><b>Working on the CLI locally</b></summary>

git clone https://github.com/FSD-CLI/cli.git
cd cli
npm install
npm test
npm run check

For bug reports, include the command you ran, framework, Node.js version, package manager, expected behavior, and actual output. Remove credentials and private project data from logs.

</details>

<div align="center">

<p><b>A clear foundation for the next thing you build.</b></p>

<p>
  Created by <b>Ashraf Mohamed</b>.<br />
  <sub>The CLI is MIT licensed. See each repository for its license.</sub>
</p>

<p>
  <a href="https://fsd-docs.vercel.app">Get started</a>
  &nbsp; · &nbsp;
  <a href="https://github.com/FSD-CLI/cli">Explore the CLI</a>
  &nbsp; · &nbsp;
  <a href="https://github.com/FSD-CLI/cli/issues">Share feedback</a>
</p>

</div>
