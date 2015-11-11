# Transpiling JavaScript ES6 to ES5 using Babel from the Command-Line

## Prerequisites

1. Install Node from [nodejs.org](http://nodejs.org).

	- Also verify that **Git** is installed.
	
2. Install **Definitely Typed**.

	```shell
	npm install tsd -g
	```

3. Download `.gitignore` file.

	```shell
	curl https://raw.githubusercontent.com/github/gitignore/master/Node.gitignore -o .gitignore
	```

4. Add a `license.md` file.

	- Paste license text: `http://choosealicense.com/licenses/mit`

## Setup

1. Install packages.

	```shell
	npm install --save-dev babel-core babel-preset-es2015
	```

2. Add a `.babelrc` file.

	```json
	{
	"presets": ["es2015"]
	}
	```
		
3. Add a `jsconfig.json` file to the folder.
	- This will remove compile errors for the ES6 files.

	```json
	{
		"compilerOptions": {
			"target": "ES6"
		}
	}
	```
			
## Write ES6 Code

1. Add js files using ES6 syntax.

	```js
	var age = 55;
	
	for (let i = 0; i < 5; i++) {
		age += 5;
	}
	
	try {
		console.log(i);
	} catch (e) {
		console.log('i is out of scope due to using let!');
	}
	```
	
2. Execute 'babel' from the command-line.
	- View the transpiled code in the command-line output.

	```shell
	babel let.js
	```

	- The following output should be shown:
	
	```js
	'use strict';
	
	var age = 55;
	
	for (var _i = 0; _i < 5; _i++) {
		age += 5;
	}
	
	try {
		console.log(i);
	} catch (e) {
		console.log('i is out of scope due to using let!');
	}
	```	