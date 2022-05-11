# React Typescript npm publishing template

This has a config for the following in order to:

    (a) Create React packages / libraries
    (b) Test said packages in storybook
    (c) load packages to npm using `npm publish` command

When done correctly a React developer should be able to execute `npm install <thisPackageName>` and integrate the built components in to their project.

## Deployment

Install sequence

```
npm init --yes
npm install --save-dev react react-dom typescript @types/react
npm i webpack webpack-cli -D
```

Create webpack.config.js

```
const path = require('path');
module.exports = {
   entry: './src/index.js',
   output: {
      filename: 'main.js',
      path: path.resolve(__dirname, 'dist'),
   },
    plugins:[
      new HtmlWebPackPlugin()
   ]
};
```

Set up dev server with hot reloading

```
npm i webpack-dev-server -D
npm i html-webpack-plugin -D
```

## Lessons Learned

Common pitfalls include:

    - using CRA Create React App to mount the project
    - inccorect specification of main attribute in package.json <"main": "dist/index.js",>

Ensure proper distinction between `devDependencies` and `peerDependencies` (see package.json)

Storybook at the time of this writing is very particular about the version of node it runs on.

```
//example install & use alterante version / or uninstall
nvm uninstall <current version>
nvm install 16.0.0
nvm use 16.0.0
node -v
```

## Authors

-  [@mdnelles](https://github.com/mdnelles)
