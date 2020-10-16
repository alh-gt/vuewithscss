# Vue.js + scss

## 実行するコマンド
```bash
git clone https://github.com/alh-gt/vuewithscss.git
git submodule init
git submodule update
npm install
npm run serve
```

## Vue.js + scss

`/src/assets/sass/variables.scss`で定義した`$red` `$blue` `$green`変数を`vue.config.js`で読み込み、`HelloWorld.vue`で使用する。

以下をサブモジュールとして配置して`HelloWorld.vue`で使用する。  
https://github.com/geoffgraham/animate.scss

## 設定系のファイルで`vue create`後の状態から変更した点
* `package.json`と同じ階層に`vue.config.js`を作成
* 以下の内容を追加  

```js
module.exports = {
    css: {
      loaderOptions: {
        scss: {
            additionalData: `@import "./src/assets/sass/variables.scss"; \
                @import "./src/assets/sass/animate/animate.scss";`
        }
      }
    }
  }
```

scssがvue-loaderで読み込まれていることだけが確認できれば良いので、
`vue create`時に作成される`HelloWorld.vue`をざっくり編集

