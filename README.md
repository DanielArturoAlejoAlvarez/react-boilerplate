# REACT Boilerplate

## Description

This repository is a Software of Application with React,NodeJS,Babel,Webpack,SASS, etc.

## Installation

Using Node,Babel,Webpack Cli, Webpack Dev Server preferably.

## DataBase

Using SQLite3,MongoDB,MySQL,etc.

## Usage

```html
$ git clone https://github.com/DanielArturoAlejoAlvarez/react-boilerplate[NAME APP]

$ npm install 

$ npm run dev (DEVELOPMENT) 

$ npm run build (PRODUCTION)
```

Follow the following steps and you're good to go! Important:

![alt text](https://camo.githubusercontent.com/af6bebd9605c5537e2251cb7c1d5b3b3def24fac/68747470733a2f2f692e6779617a6f2e636f6d2f61383936393363396165363864666433643666346138383962393730623931302e676966)

## Coding

### Config

```javascript
...
const path = require("path");
const HtmlWebpackPlugin = require("html-webpack-plugin");
const MiniCssExtractPlugin = require("mini-css-extract-plugin");

const devMode = process.env.NODE_ENV !== 'production'

module.exports = {
  entry: "./src/index.js",
  output: {
    path: path.join(__dirname, "dist"),
    filename: "bundle.js",
  },
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,
        use: ["babel-loader"],
      },
      {
        test: /\.s[ca]ss$/i,
        use: [
          {
            loader: MiniCssExtractPlugin.loader,
            options: {
              hmr: process.env.NODE_ENV === 'development',
            },
          },
          {
            loader: "css-loader"
          },
          {
            loader: "sass-loader"
          },
        ],
      },
    ],
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: "./src/index.html",
      filename: "index.html",
    }),
    new MiniCssExtractPlugin({
      filename: devMode ? '[name].css' : '[name].[hash].css',
      chunkFilename: devMode ? '[id].css' : '[id].[hash].css',
    }),
  ],
  devServer: {
    contentBase: path.join(__dirname,'dist'),
    compress:true,
    port: 9000
  }
};
...
```

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/DanielArturoAlejoAlvarez/react-boilerplate. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).

```

```
