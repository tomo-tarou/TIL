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

###データベースの導入
1. Mysqlをインストール
2. MySQLを操作するにはNode.jsからMySQLに接続する必要がある
3. mysqlパッケージをインストールする（npm install mysql）
4. MySQLに接続

![スクリーンショット 2024-01-08 16 04 46](https://github.com/ti-hiro/TIL/assets/154767207/893d8a85-3803-4078-91df-d022eae5e159)
![スクリーンショット 2024-01-08 16 05 37](https://github.com/ti-hiro/TIL/assets/154767207/8c67c6f7-8f5d-4064-a3f2-8bc6fbf2fca9)
![スクリーンショット 2024-01-08 16 05 54](https://github.com/ti-hiro/TIL/assets/154767207/de02d5f9-dd21-4626-aa42-4ebe80706d96)
![スクリーンショット 2024-01-08 16 06 21](https://github.com/ti-hiro/TIL/assets/154767207/8ce03a84-e580-40c2-827c-83d80b1a9be4)
![スクリーンショット 2024-01-08 16 09 52](https://github.com/ti-hiro/TIL/assets/154767207/04685d8a-b6bd-4b27-84af-26693d0b9886)
![スクリーンショット 2024-01-08 16 08 38](https://github.com/ti-hiro/TIL/assets/154767207/94a5c4de-ed36-4fa4-9494-4b5632079d2c)
![スクリーンショット 2024-01-08 16 11 33](https://github.com/ti-hiro/TIL/assets/154767207/2da6d0d7-8a9f-4223-9cb3-ec280938ca2a)
![スクリーンショット 2024-01-08 16 12 40](https://github.com/ti-hiro/TIL/assets/154767207/b6030b65-e16d-4f6e-a0c4-908ef6a2663c)
![スクリーンショット 2024-01-08 16 13 44](https://github.com/ti-hiro/TIL/assets/154767207/cf361ad9-a8d0-482c-bc60-02758cb5fc63)
![スクリーンショット 2024-01-08 16 14 40](https://github.com/ti-hiro/TIL/assets/154767207/2df393bc-67e2-47eb-927f-1cf7642c586c)
![スクリーンショット 2024-01-08 16 15 24](https://github.com/ti-hiro/TIL/assets/154767207/fc08bc4d-0b59-4b9a-92a0-39799cbdea11)
![スクリーンショット 2024-01-08 16 15 46](https://github.com/ti-hiro/TIL/assets/154767207/f236f326-17b1-4993-8e3d-6d1ab1b69f54)

### ルートパラメータ
- ルーティングのURLは/delete/:idのように指定する。これでURLに含まれたidを取得できるようになる。/:idの部分をルートパラメータと呼ぶ。

![スクリーンショット 2024-01-08 19 08 19](https://github.com/ti-hiro/TIL/assets/154767207/85d8ef7a-dc4d-4ad0-949a-0eecd9a77791)
![スクリーンショット 2024-01-08 19 09 12](https://github.com/ti-hiro/TIL/assets/154767207/293d1cf2-02cd-4c8f-b625-d057279edf75)
![スクリーンショット 2024-01-08 19 09 50](https://github.com/ti-hiro/TIL/assets/154767207/519a129e-5e44-4054-b845-6e96e37f615c)
![スクリーンショット 2024-01-08 19 16 42](https://github.com/ti-hiro/TIL/assets/154767207/41b8c0cd-ef5d-47da-9630-c58bb52ac6ce)
![スクリーンショット 2024-01-08 19 10 25](https://github.com/ti-hiro/TIL/assets/154767207/fd492318-63ee-478a-8a3a-845989217a18)
![スクリーンショット 2024-01-08 19 12 50](https://github.com/ti-hiro/TIL/assets/154767207/1a8d1ace-b8dc-49d7-91fe-e445d130a5d1)
![スクリーンショット 2024-01-08 19 13 00](https://github.com/ti-hiro/TIL/assets/154767207/748c5ac9-c66e-4825-89bd-f7269503e587)
![スクリーンショット 2024-01-08 19 14 42](https://github.com/ti-hiro/TIL/assets/154767207/50bea3ce-8f52-470e-be78-2bbaeb19862a)
![スクリーンショット 2024-01-08 19 15 25](https://github.com/ti-hiro/TIL/assets/154767207/24a22626-ae8f-48b8-a6bf-6f30ca2f7e19)
![スクリーンショット 2024-01-08 19 19 07](https://github.com/ti-hiro/TIL/assets/154767207/1781b35f-1b72-43ea-861f-9fba1290e49d)
![スクリーンショット 2024-01-08 19 19 26](https://github.com/ti-hiro/TIL/assets/154767207/31082521-1d62-409a-ab07-37dd85343083)
![スクリーンショット 2024-01-08 19 20 25](https://github.com/ti-hiro/TIL/assets/154767207/d033b655-a351-4bd6-a131-0d374c453f02)
![スクリーンショット 2024-01-08 19 21 01](https://github.com/ti-hiro/TIL/assets/154767207/355b0450-2780-4253-948c-8ce5b38d604c)

