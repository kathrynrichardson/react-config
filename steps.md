npm init -y

npm install react react-dom

npm install --save-dev webpack webpack-dev-server webpack-cli

npx webpack init

y to install: '@webpack-cli/generators'
use ES6
y to use webpack-dev-server
y to simplify creation of HTML files for bundle
y to add PWA support
use LESS
y to use CSS styles along with LESS
y to use PostCSS
n to not extract CSS for every file --> try criticalCSS by filamentgroup?
y to install prettier
use npm
overwrite package.json
overwrite src\index.js

//------
package.json
//------

	"scripts": {
+  	"start": "webpack-dev-server --mode development",
+  	"build": "node_modules/.in/webpack --mode production"
	}

npm install --save-dev @babel/core @babel/preset-env @babel/preset-react babel-loader

//------
.babelrc
//------

in "presets":[]
+ "@babel/preset-react"

//------
index.js
//------

- console.log("Hello World!");

import React from "react";
import { createRoot } from 'react-dom/client';
import App from './App';

const element = document.getElementById('root');
const root = createRoot(element);

root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

//------
App.js
/------

import React from "react";
import { createRoot } from 'react-dom/client';
import App from './App';

const element = document.getElementById('root');
const root = createRoot(element);

root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

//------
./dist/index.html
//-----

<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="utf-8" name="viewport" content="width=device-width, initial-scale=1" />
		<title>Webpack App</title>
		<script defer src="main.js"></script>
	</head>
	<body>
		<div id="root">test</div>
	</body>
</html>

//------
.prettierrc
//------

{
	"tabWidth": 2,
	"printWidth": 100,
	"semi": true,
	"singleQuote": true,
	"trailingComma": "es5",
	"useTabs": true
}

//------
settings.json
//------

{
	"editor.formatOnSave": true,
	"prettier.eslintIntegration": true,
	"files.trimTrailingWhitespace": true,
	"files.insertFinalNewline": true,
	"files.trimFinalNewlines": true
}

npm install --save styled-components@5.3.10