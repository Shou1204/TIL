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

### 切り上げ整数にする
```javascirpt
let damage = Math.floor(Math.random() * 10);
```

## if文
基本形
```javascript
if (条件式1) {
    処理1;
} else {
    処理2;
}
```
### if文による簡単な占い
```javascript
process.stdin.resume();
process.stdin.setEncoding('utf8');
var number = parseInt(Math.random() * 10) + 1;
if (number % 2 == 0) {
    console.log("好き！");
} else {
    console.log("嫌い！");
}
```

### 日付を取得する new Date()メソッド
```javascript
//今日の日付データを変数hidukeに格納
var hiduke = new Date(); 

//年・月・日・曜日を取得する
var year = hiduke.getFullYear();
var month = hiduke.getMonth()+1;
var week = hiduke.getDay();
var day = hiduke.getDate();

var yobi= new Array("日","月","火","水","木","金","土");

document.write("西暦"+year+"年"+month+"月"+day+"日 "+yobi[week]+"曜日");
```

## 繰り返し処理

### whileメソッド
```javascript
while (条件式){
    繰り返し処理
}
```

### forメソッド
```javascript
for (条件式に使う変数の初期化処理; 条件式; 条件式に使う変数の値の更新) {
    繰り返し処理
}
```

## javascriptでの標準入力

```javascript
process.stdin.resume();
process.stdin.setEncoding('utf8');

var input_string = "";
var reader = require('readline').createInterface({
    input: process.stdin,
    output: process.stdout
});
reader.on('line', (line) => {
    input_string = line
});
reader.on('close', () => {
    var input_int = parseInt(input_string)
    var result = input_int + 100;
    console.log(result);
});
```
- 標準入力で与えられるのは文字列なため、数値にするなら`parseInt関数`で変換する必要がある
```javascript
// 標準入力からテキストを取得する

process.stdin.resume();
process.stdin.setEncoding('utf8');

var input_string = "";
var reader = require('readline').createInterface({
    input: process.stdin,
    output: process.stdout
});
reader.on('line', (line) => {
    // ここで入力を処理する
    input_string = line
});
reader.on('close', () => {
    // ここで出力する
    console.log(input_string)
});
```
