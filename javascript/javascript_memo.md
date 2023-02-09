# javascriptの学習メモ
- JavaScriptのプログラムで改行しない場合、`process.stdout.write`（スタンダードアウト ライト）関数を使う。
```javascript
process.stdout.write("hello world")
```

---
### ランダムな数字を表示する
```javascript
process.stdin.resume();
process.stdin.setEncoding('utf8');
var randnum = parseInt(Math.random() * 10) + 5;
console.log("スライムが" + randnum + "匹あらわれた");
```
`Math.random()`関数が0~1のランダム数値を出力 

`* 10`,`+5`は5~10の範囲に絞るため

`parseInt()関数`は整数に直すため

---

