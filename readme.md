<a href="https://github.com/transitive-bullshit/chatgpt-plugin-ts">
  <img alt="ChatGPT Plugin TS" src="/media/social.png">
</a>

<h1 align="center">ChatGPT Plugin TS</h1>

<p align="center">
  Examples and resources for creating ChatGPT plugins in TypeScript.
</p>

<p align="center">
  <a href="https://www.npmjs.com/package/chatgpt-plugin"><img alt="chatgpt-plugin NPM package" src="https://img.shields.io/npm/v/chatgpt-plugin.svg" /></a>
  <a href="https://github.com/transitive-bullshit/chatgpt-plugin-ts/actions/workflows/test.yml"><img alt="Build Status" src="https://github.com/transitive-bullshit/chatgpt-plugin-ts/actions/workflows/test.yml/badge.svg" /></a>
  <a href="https://github.com/transitive-bullshit/chatgpt-plugin-ts/blob/main/license"><img alt="MIT License" src="https://img.shields.io/badge/license-MIT-blue" /></a>
  <a href="https://prettier.io"><img alt="Prettier Code Formatting" src="https://img.shields.io/badge/code_style-prettier-brightgreen.svg" /></a>
</p>

- [Intro](#intro)
- [Install](#install)
- [Example Plugins](#example-plugins)
  - [Dexa Lex Fridman Plugin](#dexa-lex-fridman-plugin)
  - [ASCII Art Plugin](#ascii-art-plugin)
- [Notes](#notes)
- [License](#license)

## Intro

This repo contains the [chatgpt-plugin NPM package](./packages/chatgpt-plugin), with TS types and utilities for building ChatGPT Plugins with TypeScript.

It also contains several high quality example plugins that you can use as a template for building your own plugins. The goal is to add more examples using different OpenAPI frameworks and hosting providers over time. Currently, all of the examples use Cloudflare Workers, but I'll add an example using Vercel serverless functions soon.

If there's something missing that you'd like to see, please [open an issue](https://github.com/transitive-bullshit/chatgpt-plugin-ts/issues/new) or join our [ChatGPT Hackers community](https://www.chatgpthackers.dev/) on Discord, with over 8000 developers who are building cool stuff with AI!

## Install

```bash
npm install chatgpt-plugin
# or
yarn add chatgpt-plugin
# or
pnpm install chatgpt-plugin
```

## Config
Start by adding your aiPlugin configuration into the `package.json` file like so: 
(see full instructions on [OpenAi docs](https://platform.openai.com/docs/plugins/getting-started/plugin-manifest))
```json
  "aiPlugin": {
    "name": "plugin_name",
    "description_for_model": "description_for_model",
    "logo_url": "hosted logo url",
    "contact_email": "your email",
    "legal_info_url": "legal info link"
  }
```


## Example Plugins

TS code for all example plugins can be found in the [examples](/examples) directory.

### Dexa Lex Fridman Plugin

Example ChatGPT retrieval plugin to search across all of the [Lex Fridman Podcast](https://lexfridman.com/podcast/) episodes – powered by [Dexa AI](https://dexa.ai).

- [source code](/examples/dexa-lex-fridman)
- [launch tweet](https://twitter.com/transitive_bs/status/1643990888417464332)
- built using CF workers

<p align="center">
  <img src="/media/advice-for-youth-opt.jpg" alt="What advice does Lex's podcast have for young people?" width="45%">
  &nbsp;&nbsp;&nbsp;

  <img src="/media/elon-musk-philosophy-on-life-opt.jpg" alt="What is Elon Musk's philosophy on life?" width="45%">
</p>

<p align="center">
  <img src="/media/poker-and-physics-opt.jpg" alt="What do poker and physics have in common?" width="45%">
  &nbsp;&nbsp;&nbsp;

  <img src="/media/love-opt.jpg" alt="What do Lex's guests think about love?" width="45%">
</p>

### ASCII Art Plugin

This is a really simple example plugin that converts text to ASCII art. It's a great template to start building your own plugins.

- [source code](/examples/ascii-art/)
- [launch tweet](https://twitter.com/transitive_bs/status/1643144204900597760)
- built using CF workers

<p align="center">
  <img src="/media/plugin-ascii-art-demo-opt.jpg" alt="ASCII art using the Poison font" width="45%">
</p>

## Notes

- `name_for_human`
  - 30 character max
- `name_for_model`
  - 50 character max
- `description_for_human`
  - 120 character max
- `description_for_model`
  - 8000 character max
  - Max decreases over time
- API response body length
  - 100k character limit
  - Decreases over time
  - Subject to limitations
- TODO: `defineConfig` function to help validate `ai-plugin.json` configs?

## License

MIT © [Travis Fischer](https://transitivebullsh.it)

If you found this project interesting, please consider [sponsoring me](https://github.com/sponsors/transitive-bullshit) or <a href="https://twitter.com/transitive_bs">following me on twitter <img src="https://storage.googleapis.com/saasify-assets/twitter-logo.svg" alt="twitter" height="24px" align="center"></a>
