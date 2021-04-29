# vue-webpack
---
웹팩에 간략한 설명은 react-webpack에서 하였으므로 설치에 관해서만 정리하겠다.

https://github.com/apateonos/react-webpack

## Vue 설치
프로젝트를 진행할 디렉토리로 이동하여 준뒤 `npm init`으로 npm을 설정하여주고 `vue`를 설치하여준다.
```
npm init
...
npm i --save vue
```

### vue-loader template-compliar 설치
이전 react 에서 처럼 webpack을 사용하기 위한 loader와 compliar를 설치하여준다.
```
npm i --save-dev vue-loader vue-template-compiler
```

### babel설치
vue도 자바스크립트 문법이므로 babel을 이용하여 webpack에서 컴파일 시켜주겠다.
```
npm i --save-dev @babel/core @babel/preset-env babel-loader
```

### webpack 및 loader설치
```
npm i --save-dev webpack webpack-cli webpack-dev-server html-loader html-webpack-plugin
```

### webpack.config.js생성
```webpack.config.js
const VueLoaderPlugin = require("vue-loader/lib/plugin");

module.exports = {
  module: {
    rules: [
      ...
      {
        test: /\.vue$/,
        loader: "vue-loader"
      }
    ]
  },
  resolve: {
    alias: {
      "vue$": "vue/dist/vue.esm.js"
    },
    extensions: ['*', '.js', '.vue', '.json']
  },
  plugins: [
    ...
    new VueLoaderPlugin()
  ]
};
```
