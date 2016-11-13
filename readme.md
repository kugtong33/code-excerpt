# code-excerpt [![Build Status](https://travis-ci.org/vdemedes/code-excerpt.svg?branch=master)](https://travis-ci.org/vdemedes/code-excerpt) [![Coverage Status](https://coveralls.io/repos/github/vdemedes/code-excerpt/badge.svg?branch=master)](https://coveralls.io/github/vdemedes/code-excerpt?branch=master)

> Extract code excerpts


## Install

```
$ npm install --save code-excerpt
```


## Usage

```js
const codeExcerpt = require('code-excerpt');

const source = `
'use strict';

function someFunc() {}

module.exports = () => {
	const a = 1;
	const b = 2;
	const c = 3;

	someFunc();
};
`.trim();

const excerpt = codeExcerpt(source, 5);
//=> [
//	{line: 2, value: '                        '},
//	{line: 3, value: 'function someFunc() {}  '},
//	{line: 4, value: '                        '},
//	{line: 5, value: 'module.exports = () => {'},
//	{line: 6, value: '  const a = 1;          '},
//	{line: 7, value: '  const b = 2;          '},
//	{line: 8, value: '  const c = 3;          '}
// ]
```


## API

### codeExcerpt(source, line, [options])

All lines in the output have equal width for convenience.
For example, if a line needs to be highlighted, the highlight will be full-width, just like in editors.

#### source

Type: `string`

Source code.

#### line

Type: `number`

Line number to extract excerpt for.

#### options

##### around

Type: `number`<br>
Default: `3`

Number of surrounding lines to extract.


## License

MIT © [vdemedes](https://github.com/vdemedes)
