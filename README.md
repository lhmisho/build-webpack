# build-webpack

# build-webpack

**Isnstruction to build web-pack** 

**Tools**
1) Babel
2) Webpack

Step:1 -- install node package manager.
----------------------------------------
```js
npm init -y
```

Step:2 -- Install babel
-----------------------
```js
npm install --save-dev @babel/core @babel/preset-env
npm install --save-dev @babel/preset-react // for react
```
step:3 -- create .babelrc -- include the following
----------------------------------------
```js
{
  "presets": [
    "@babel/preset-env",
    "@babel/preset-react"
  ]
}
```

Step:4 -- install dev server
----------------------------
```js
npm install webpack-dev-server --save-dev
```

Step:5 -- Install webpack to bundle the code
---------------------------------------------
```js
npm install --save-dev webpack babel-loader
npm install --save-dev sebpack-cli -D
```
Create webpack.onfig.js
-----------------------
```js
const path = require('path');

const config = {
    entry: './src/index.js',
    output: {
        path: path.resolve(__dirname, 'dist'),
        filename: 'bundle.js'
    },

    module: {
        rules: [
            {
                test: /\.js$/,
                use: {
                    loader: 'babel-loader'
                }
            }
        ]
    }
}

module.exports = config;
```

Edit scipt on package.json
--------------------------
```js
"scripts": {
    "dev": "webpack --mode development",
    "build": "webpack --mode production",
    "start": "webpack-dev-server"
  },
```
