# React
- Reactは、JSのライブラリ（サイトの見た目を作ることができる）
- React Nativeは、iOS・Android両方のスマホアプリを作成可能

## JSX
### JSXの書き方
- JSXは、HTMLとほとんど同じように記述することができる。
- 見出しにはh1タグやh2タグ、文章にはpタグ、その他divタグなど、HTMLと同様のタグが使えるようになっている
### JSXの注意点
- return内に複数の要素があるとエラーになるので、複数の要素がある場合は、<div>タグで囲んで一つの要素にまとめる
```
render() {
  return (
    <div>
      <h1>h1です</h1>
      <h2>h2です</h2>
      <h3>h3です</h3>
    </div>
  );
}
```
### JSXのコメント
- JSXを{/* */}で囲むと、その部分はコメントになる
- JavaScriptのコメントは文頭に//を書く
### imgタグの注意点
- imgタグは、HTMLでは、<**img** src='画像のURL'>のように閉じタグが必要なかったが、JSXでは閉じタグが必要になる
- <**img** src='画像のURL' />のように、タグの終わりにスラッシュ「/」を記述する

## App.jsの構成
![スクリーンショット 2024-01-04 13 16 20](https://github.com/ti-hiro/TIL/assets/154767207/733bb863-8141-4fe6-befd-dced577ed6e9)

## JSXとJS
### JSXとJSの範囲
- JSXとJS ( JavaScript ) の記述部分は分かている
- renderメソッドのreturn内のみ、JSXで記述する必要がある。JSXで記述された要素はブラウザに表示される。
- renderメソッドの、returnの外にはJavaScriptを記述可能
- JavaScriptの部分を中括弧{ }で囲めば、returnの中でも、JSXにJavaScriptを埋め込むことが出来る
```
render() {
  const imgUrl = 'https://~~~.png';
  return (
    <img src= { imgUrl }/>
  );
```
}
## クリックと表示の切り替え
- ユーザーがボタンをクリックした時に、表示名が切り替わるようにするには、イベントとstateが必要
- まずbuttunタグを作る
### イベント
- イベントを用いると、「何かが起きたときに、処理を実行するように指定」することができる（例：ボタンをクリックした時に表示名が切り替わるようにする）
- タグ内に、イベント名={() => { 処理 }}と書くことで、指定したタイミングで処理を実行できる。
- アロー関数はJavaScriptなので、{}で囲むこと
- onClickイベントは、クリックされた時に処理を実行する」イベント。
- イベント名にonClickを指定し、<button onClick={() => {処理}}>とする

### state
- ユーザーの動きに合わせて変わる値のことを、Reactではstateと呼ぶ
- stateを使って、表示を変えるには3つのステップが必要
  - step1: stateの定義
  - step2: stateの表示
  - step3: stateの変更
#### stateの定義(step1)
- stateの定義では、「オブジェクト」を使用する(つまりstateは、オブジェクトという扱い）
- 「オブジェクト」は、複数の値をプロバティという名前をつけて、管理できるもの
```
const user = { name: ”にんじゃにゃんこ”、age: 3 } ←　プロバティと値のセット
console.log(user.age); ←「定数名.プロバティ名」で値を取得
```
 - stateは、constructorの中で、オブジェクトとして定義する。ここで定義したオブジェクトがstateの初期値になる。
 - 「constructor(props)」や「super(props);」といった処理はいつも同じ記述をするため、定型文として覚えておけば大丈夫
```
class App extends React.Component {
  constructor(props) {
    super(props);
    this.state = {name: 'にんじゃわんこ'};
  }
}
```
#### stateの表示(step2)
- 定義したstateは、this.stateで取得することができる
- stateはオブジェクトなので、console.log(this.state)をするとオブジェクトが出力される
- this.stateはオブジェクトなので、this.state.プロパティ名とすることで、指定したstateのプロパティ名に対応する値を取得できる
#### stateの変更(step3)
- ボタンがクリックされた時に、名前の表示が切り替わるようにするには、stateの変更とonClickイベントを使う
- this.setState({プロパティ名: 変更する値})とすることで、指定されたプロパティに対応するstateの値が変更される。その結果、「this.state.name」で表示できる値も変更さる

![スクリーンショット 2024-01-04 14 52 09](https://github.com/ti-hiro/TIL/assets/154767207/f8222675-3b11-492c-b811-f3321c0eb9ae)

- メソッドは、クラスの中で定義する。処理のまとまりを定義できるもの。メソッド名() { 処理 }で定義できる。

![スクリーンショット 2024-01-04 15 00 52](https://github.com/ti-hiro/TIL/assets/154767207/68f4bc7c-f7d7-4208-b374-33b36d06ef0a)

### ブラウザに表示される流れ
![スクリーンショット 2024-01-04 16 52 56](https://github.com/ti-hiro/TIL/assets/154767207/657a2ee5-be4a-4f08-a5e7-4812a3b556f4)
![スクリーンショット 2024-01-04 16 54 00](https://github.com/ti-hiro/TIL/assets/154767207/6b1fd930-7cbf-472a-852f-ece1ae38d239)
![スクリーンショット 2024-01-04 16 54 16](https://github.com/ti-hiro/TIL/assets/154767207/17d44857-1a48-400e-a521-76847fffcddf)
- JSXにクラス名をつける場合、HTMLと書き方が違うため注意
- className='クラス名'」とする
- CSSの指定方法は変わらない

### コンポーネント
- コンポーネントは「部品」や「パーツ」という意味
- Reactでは、見た目を機能ごとにコンポーネント化して、コンポーネントを組み合わせることでWebサイトの見た目を作る

![スクリーンショット 2024-01-04 16 57 30](https://github.com/ti-hiro/TIL/assets/154767207/f5e303e3-146b-4220-af43-68bf3cba4ff4)
![スクリーンショット 2024-01-04 16 57 47](https://github.com/ti-hiro/TIL/assets/154767207/f6690508-9c63-412a-b5a0-444744967461)
![スクリーンショット 2024-01-04 16 58 07](https://github.com/ti-hiro/TIL/assets/154767207/c2e1b32c-b8da-436e-b3be-ca1ec66ad8fe)
![スクリーンショット 2024-01-04 16 58 40](https://github.com/ti-hiro/TIL/assets/154767207/0a208c5e-f674-46bc-8a7e-8bc30b2e075c)
![スクリーンショット 2024-01-04 16 59 27](https://github.com/ti-hiro/TIL/assets/154767207/d83dde72-bc3c-4717-8766-63a8a99c75be)
#### コンポーネントの特徴
- コンポーネントは一度作れば、何度でも呼び出すことができる

### props
#### propsとは
- propsとは、コンポーネントに渡されるデータのことを指す。「properties（プロパティ）」の略称で、コンポーネントの外部から与えられるデータや設定を表す。
- propsを使うことで、コンポーネントは再利用可能で柔軟なものになる

![スクリーンショット 2024-01-04 17 01 41](https://github.com/ti-hiro/TIL/assets/154767207/e68c60e0-68a7-4ab5-851e-d78bdc914c39)
![スクリーンショット 2024-01-04 17 03 31](https://github.com/ti-hiro/TIL/assets/154767207/17b814e1-19f6-48e5-8e3d-d80edce4660d)
![スクリーンショット 2024-01-04 17 04 23](https://github.com/ti-hiro/TIL/assets/154767207/f2c0c9f2-a6bf-4cd3-bfa0-78b5e187009f)
![スクリーンショット 2024-01-04 17 04 47](https://github.com/ti-hiro/TIL/assets/154767207/d24c10cc-8d46-408a-a7df-177399a08c8f)
#### コンポーネントを何度も呼び出すには
![スクリーンショット 2024-01-04 17 06 29](https://github.com/ti-hiro/TIL/assets/154767207/181f0b44-360e-4757-a89d-c76409875f2f)
![スクリーンショット 2024-01-04 17 06 56](https://github.com/ti-hiro/TIL/assets/154767207/8f0c3acc-27ac-4f8f-8062-37f5801f3e33)

### コンポーネントの作り方
![スクリーンショット 2024-01-04 21 33 18](https://github.com/ti-hiro/TIL/assets/154767207/bc2850a7-df36-43dc-a33b-8dbd9d21cf33)
### コンポーネントの表示
![スクリーンショット 2024-01-04 21 34 28](https://github.com/ti-hiro/TIL/assets/154767207/75b634c6-5842-4f91-aa32-25ae4ad1df2b)
### propsを渡す
![スクリーンショット 2024-01-04 21 35 32](https://github.com/ti-hiro/TIL/assets/154767207/ec8437c8-78f9-46cc-8813-e612c5fe3b2e)
### propsを受け取る
![スクリーンショット 2024-01-04 21 36 14](https://github.com/ti-hiro/TIL/assets/154767207/90e6461f-8320-433d-959c-01a471a0c4a2)

### モーダルの作成
![スクリーンショット 2024-01-04 21 37 19](https://github.com/ti-hiro/TIL/assets/154767207/cd04956d-89da-4ae9-a49f-68635cfa5152)
### モーダルの表示・非表示
![スクリーンショット 2024-01-04 21 40 31](https://github.com/ti-hiro/TIL/assets/154767207/d824705a-6cd7-48e5-b5fa-cd91180dc2f5)
### stateの定義
![スクリーンショット 2024-01-04 21 41 35](https://github.com/ti-hiro/TIL/assets/154767207/2a9afd89-1f13-42f2-baca-20bb365573f9)
### JSXとif文
![スクリーンショット 2024-01-04 21 43 56](https://github.com/ti-hiro/TIL/assets/154767207/12f70b6d-904a-4ad5-8b90-0279b52750c8)
![スクリーンショット 2024-01-04 21 44 08](https://github.com/ti-hiro/TIL/assets/154767207/d9ce7f14-8d94-45ce-89aa-876c24ccbd0f)
### モーダルを表示する
![スクリーンショット 2024-01-04 21 44 56](https://github.com/ti-hiro/TIL/assets/154767207/67190891-ca90-48e0-bc7b-f5934e20f55a)
### モーダルを非表示にする
![スクリーンショット 2024-01-04 21 46 05](https://github.com/ti-hiro/TIL/assets/154767207/f599b5bf-7544-44de-a3e7-d4c58a0a18f8)


