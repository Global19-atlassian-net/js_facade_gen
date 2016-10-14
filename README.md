[![Build Status](https://travis-ci.org/dart-lang/js_facade_gen.svg?branch=master)](https://travis-ci.org/dart-lang/js_facade_gen)

Generates `package:js` Javascript interop facades for arbitrary TypeScript
libraries.

## Installation

- [Install Node.js](https://docs.npmjs.com/getting-started/installing-node)
   - We depend on Node.js so that we can analyze TypeScript files using the [TypeScript language services](https://www.npmjs.com/package/typescript-services) package. This ensures we parse `d.ts` consistently with other tools.
- Execute `npm i` to install the dependencies.
- The Dart SDK must be available to run end to end tests.

## Usage

### Basic
`node build/lib/main.js <input d.ts file>`
Dart interop facade file is written to stdout.

### Advanced
`node build/lib/main.js --destination=<destination-dir> --basePath=<input d.ts file directory> <input d.ts file> <input d.ts file> ...`

### Example
`node build/lib/main.js --destination=/usr/foo/tmp/chartjs/lib --basePath=/usr/foo/git/DefinitelyTyped/chartjs /usr/foo/git/DefinitelyTyped/chartjs/chart.d.ts`

## Gulp tasks

- `gulp watch` executes the unit tests in watch mode (use `gulp test.unit` for a single run),
- `gulp test.e2e` executes the e2e tests,
- `gulp test.check-format` checks the source code formatting using `clang-format`,
- `gulp test` runs unit tests, e2e tests and checks the source code formatting.

## Publish

 - `npm run prepublish`
 - `npm publish`