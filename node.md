## Node.jsとは
- Node.jsは本来クライアント側の言語であるJavaScriptをサーバーサイドで動かすための仕組み
- 多くのWebアプリの仕組みや作り方の基本は変わらない
### Express
- ExpressはNode.jsでWebアプリの開発をするためのフレームワーク。フレームワークを利用することで開発を効率化することができる。
### パッケージ
- Node.jsには便利な機能を簡単に使えるようにまとめたパッケージというものがある。Expressもパッケージの１つ
### npm
- パッケージを用意するにはnpm (Node Package Manager)というシステムを使う
- npmにはパッケージを共有・取得する機能がある
- npm installコマンドを使って、インターネットから自分のアプリケーションにパッケージをインストールできる
  - 例： npm install express
#### インストールしたExpressを利用する
```
const express = require('express');  ← expressの読み込み
const app = express(); ←　expressを使用するための準備
```
### listenメソッド
![スクリーンショット 2024-01-08 15 36 47](https://github.com/ti-hiro/TIL/assets/154767207/f10b5a2b-d81e-4d5f-bc96-b5c23b87e517)
### ルーティング
![スクリーンショット 2024-01-08 15 37 28](https://github.com/ti-hiro/TIL/assets/154767207/d7ba533e-a7b5-4597-950f-543bc453c66a)
### reqとres
![スクリーンショット 2024-01-08 15 38 09](https://github.com/ti-hiro/TIL/assets/154767207/d180a43b-f5ea-41b4-a2ad-ff4844ac22b1)
- ブラウザに表示する見た目部分にはEJSという形式のファイルを使い、viewsフォルダに配置する
- ルーティングの処理でres.renderと書くことで、指定したビューファイルをブラウザに表示できる
![スクリーンショット 2024-01-08 15 40 18](https://github.com/ti-hiro/TIL/assets/154767207/2a2b1e7f-1b58-4e29-8ec8-64ef9ec5e14e)
![スクリーンショット 2024-01-08 15 40 41](https://github.com/ti-hiro/TIL/assets/154767207/e985129f-b2c7-4fe9-8123-69d9cc402e1d)
### EJSとは
![スクリーンショット 2024-01-08 15 42 40](https://github.com/ti-hiro/TIL/assets/154767207/891d7e16-cadd-46b4-9e5d-aaed4e99a248)
- npm install ejsでインストールすることで使える
- HTML内でJavaScriptのコードを記述するには、<% %>または<%= %>で囲む
- <% %>で囲んだ場合はブラウザには何も表示されないので、変数の定義などに使用する
- <%= %>は、変数の値などをブラウザに表示したい場合に使用
![スクリーンショット 2024-01-08 15 46 24](https://github.com/ti-hiro/TIL/assets/154767207/4db25f28-ad92-498a-a467-a0bb3375620d)
![スクリーンショット 2024-01-08 15 46 43](https://github.com/ti-hiro/TIL/assets/154767207/5ef13184-a03f-4d5e-a871-c73711a3a8dd)
