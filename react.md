- Reactは、JSのライブラリ（サイトの見た目を作ることができる）
- React Nativeは、iOS・Android両方のスマホアプリを作成可能

## JSX
### JSXの書き方
- JSXは、HTMLとほとんど同じように記述することができる。
- 見出しには<h1>タグや<h2>タグ、文章には<p>タグ、その他<div>タグなど、HTMLと同様のタグが使えるようになっている
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
-　ユーザーがボタンをクリックした時に、表示名が切り替わるようにするには、イベントとstateが必要
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

