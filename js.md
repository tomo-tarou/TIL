### コールバック関数
- JavaScriptでは引数に関数を渡すことができる
- 引数に渡される関数をコールバック関数と呼ぶ
- 関数は、関数名の後ろに()をつけると呼び出され、()をつけなければ関数そのものを指す
```
callback(); ←　関数を呼び出す時は()をつける

call(printWanko) ←　コールバック関数を渡す時は()をつけない
```

```
const printWanko = () => {
  console.log("にんじゃわんこ");
};

// 関数callにcallbackという名前の引数を追加
const call = (callback) => {
  console.log("コールバック関数を呼び出します。");
  // 引数に渡したcallbackを呼び出す
  callback();
};

// 関数printWankoを引数に渡して関数callを実行
call(printWanko);
```
![スクリーンショット 2024-01-03 23 48 06](https://github.com/ti-hiro/TIL/assets/154767207/a2e0c979-3985-49f6-8439-3fcce9dae22c)
![スクリーンショット 2024-01-03 23 48 44](https://github.com/ti-hiro/TIL/assets/154767207/926f79bc-8479-4e45-9140-077138eb3886)
![スクリーンショット 2024-01-03 23 49 02](https://github.com/ti-hiro/TIL/assets/154767207/2a5d32c0-d895-4aca-a170-49d2ab13d507)
![スクリーンショット 2024-01-03 23 49 20](https://github.com/ti-hiro/TIL/assets/154767207/b22df79e-ec72-45f7-bb12-e985cff5ca8c)
