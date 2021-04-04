





버전 체크

- 짝수버전으로 사용

- node -v

- npm -v



실행환경

1. $ npm init
   $ npm init -y ==> 물어보는거 없이 알아서 셋팅



2. webpack 관련 설치
   npm i -D webpack
   npm i -D webpack-cli
   npm i -D webpack-dev-server   => 실시간 reload 서버
   npm i -D webpack-merge => config 병합

   * webpack  config 설정

     - webpack.config.js 생성

       ```javascript
       const path = require('path')
       
       Model.exports = {
         // 진입점
         entry: {
           
         },
         // 결과물에 대한 설정
         output: {
           
         },
         modules: {},
         plugins: []
       }
       ```

3. Vue Loader 설치
   npm install -D vue-loader vue-template-compiler

   * loader 설정

     * webpack.config.js 설정

       ```javascript
       const { VueLoaderPlugin } = require('vue-loader')
       
       module.exports = {
         module: {
           rules: [
             // ... other rules
             {
               test: /\.vue$/,
               loader: 'vue-loader'
             }
           ]
         },
         plugins: [
           // make sure to include the plugin!
           new VueLoaderPlugin()
         ]
       }
       
       ```

4. Vue 개발을 할때 유용한 유틸 - Vetur ( Optional )
   - vscode 에서 확장-마켓플렛이스로 설치

5. Vue 설치
   npm i vue

   * App.vue 설정 변경
     render: h => h(App)

6. loader 설치 / 설정
   js 해석 => babel

   * npm i -D babel-loder

   css 해석 => vue-styple-loader, css-loader

   * npm i -D vue-styple-loader css-loader

   ```javascript
   const { VueLoaderPlugin } = require('vue-loader')
   
   module.exports = {
     mode: 'development',
     module: {
       rules: [
         {
           test: /\.vue$/,
           loader: 'vue-loader'
         },
         // this will apply to both plain `.js` files
         // AND `<script>` blocks in `.vue` files
         {
           test: /\.js$/,
           exclude: /node-modules/,
           loader: 'babel-loader'
         },
         // this will apply to both plain `.css` files
         // AND `<style>` blocks in `.vue` files
         {
           test: /\.css$/,
           use: [
             'vue-style-loader',
             'css-loader'
           ]
         }
       ]
     },
     plugins: [
       // make sure to include the plugin for the magic
       new VueLoaderPlugin()
     ]
   }
   ```

   





