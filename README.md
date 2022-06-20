# web3 scaffold

_Quickly get up and running on web3_

1. clone the repo
2. `cd web3-scaffold`
3. `pnpm install`
4. `pnpm run dev`

This scaffold is set up as a monorepo using the incredibly fast [pnpm](https://pnpm.io/), with packages for each part of the project. All of these packages use  a common [Typescript](https://www.typescriptlang.org/) foundation with [linting](https://eslint.org/) and [autoformatting](https://prettier.io/) and is best used with [VSCode](https://code.visualstudio.com/). It assumes you'll be deploying to an [EVM-compatible blockchain](https://chainlist.org/).


## Packages

### app

This is the frontend of your project. It's built on [Next.js](https://nextjs.org/) using [Tailwind CSS](https://tailwindcss.com/). Data is read from the smart contract via a subgraph (below) using [urql](https://formidable.com/open-source/urql/) and autogenerated Typescript definitions with [GraphQL Code Generator](https://www.graphql-code-generator.com/).

### contracts

This is where your smart contracts live. They're written in [Solidity](https://docs.soliditylang.org/) using [Foundry (forge & cast)](https://book.getfoundry.sh/) to compile, test, and deploy. Types are generated with [TypeChain](https://github.com/dethcrypto/TypeChain).

### subgraph

This is the read-only backend for your project and where you can offload a lot of the heavy lifting that would traditionally be done through an eth RPC node. It's written in [AssemblyScript](https://www.assemblyscript.org/) and deployed to [The Graph](https://thegraph.com/).


## Deploying

### Vercel

Vercel supports monorepos and pnpm out-of-the-box, but you'll need to set the "Root Directory" to `packages/app` either during the Vercel project setup or afterwards in the project settings.
