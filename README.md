<div align="center">
   <img src="https://res.cloudinary.com/adonisjs/image/upload/q_100/v1564392111/adonis-banner_o9lunk.png" width="600px">
</div>

# Encryption
> AdonisJs provider to encrypt and decrypt values

[![circleci-image]][circleci-url] [![npm-image]][npm-url] ![][typescript-image] [![license-image]][license-url]

This module is used by [AdonisJs](https://adonisjs.com) to encrypt/decrypt values using a secret key.

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
## Table of contents

- [Usage](#usage)
- [Using with AdonisJs](#using-with-adonisjs)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Usage

Install the package from npm registry as follows:

```sh
npm i @adonisjs/encryption

# yarn
yarn add @adonisjs/encryption
```

and then use it as follows:

```ts
import { Encryption } from '@adonisjs/encryption/build/standalone'
const encryption = new Encryption({ secret: 'verylongandrandom32characterskey' })

const encryptedValue = encryption.encrypt('hello-world')
encryption.decrypt(encryptedValue) // 'hello-world'
```

## Using with AdonisJs
The `@adonisjs/core` module includes this module by default. However, here's how you can set it up manually.

```ts
const providers = [
  '@adonisjs/encryption'
]
```

And then also register the typings file inside `tsconfig.json` file.

```json
{
  "files": ["./node_modules/@adonisjs/encryption/build/adonis-typings/encryption.d.ts"]
}
```

And use it as follows:

```ts
import Encryption from '@ioc:Adonis/Core/Encryption'
Encryption.encrypt('password')
```

[circleci-image]: https://img.shields.io/circleci/project/github/adonisjs/encryption/master.svg?style=for-the-badge&logo=circleci
[circleci-url]: https://circleci.com/gh/adonisjs/encryption "circleci"

[typescript-image]: https://img.shields.io/badge/Typescript-294E80.svg?style=for-the-badge&logo=typescript
[typescript-url]:  "typescript"

[npm-image]: https://img.shields.io/npm/v/@adonisjs/encryption.svg?style=for-the-badge&logo=npm
[npm-url]: https://npmjs.org/package/@adonisjs/encryption "npm"

[license-image]: https://img.shields.io/npm/l/@adonisjs/encryption?color=blueviolet&style=for-the-badge
[license-url]: LICENSE.md "license"
