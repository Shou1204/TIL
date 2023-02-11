# javascript の学習メモ

- JavaScript のプログラムで改行しない場合、`process.stdout.write`（スタンダードアウト ライト）関数を使う。

```javascript
process.stdout.write("hello world");
```

---

### ランダムな数字を表示する

```javascript
process.stdin.resume();
process.stdin.setEncoding("utf8");
var randnum = parseInt(Math.random() * 10) + 5;
console.log("スライムが" + randnum + "匹あらわれた");
```

`Math.random()`関数が 0~1 のランダム数値を出力

`* 10`,`+5`は 5~10 の範囲に絞るため

`parseInt()関数`は整数に直すため

---

### 切り上げ整数にする

```javascirpt
let damage = Math.floor(Math.random() * 10);
```

## if 文

基本形

```javascript
if (条件式1) {
  処理1;
} else {
  処理2;
}
```

### if 文による簡単な占い

```javascript
process.stdin.resume();
process.stdin.setEncoding("utf8");
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
var month = hiduke.getMonth() + 1;
var week = hiduke.getDay();
var day = hiduke.getDate();

var yobi = new Array("日", "月", "火", "水", "木", "金", "土");

document.write(
  "西暦" + year + "年" + month + "月" + day + "日 " + yobi[week] + "曜日"
);
```

## 繰り返し処理

### while メソッド

```javascript
while (条件式) {
  繰り返し処理;
}
```

### for メソッド

```javascript
for (条件式に使う変数の初期化処理; 条件式; 条件式に使う変数の値の更新) {
  繰り返し処理;
}
```

## javascript での標準入力

```javascript
process.stdin.resume();
process.stdin.setEncoding("utf8");

var input_string = "";
var reader = require("readline").createInterface({
  input: process.stdin,
  output: process.stdout,
});
reader.on("line", (line) => {
  input_string = line;
});
reader.on("close", () => {
  var input_int = parseInt(input_string);
  var result = input_int + 100;
  console.log(result);
});
```

- 標準入力で与えられるのは文字列なため、数値にするなら`parseInt関数`で変換する必要がある

```javascript
// 標準入力からテキストを取得する

process.stdin.resume();
process.stdin.setEncoding("utf8");

var input_string = "";
var reader = require("readline").createInterface({
  input: process.stdin,
  output: process.stdout,
});
reader.on("line", (line) => {
  // ここで入力を処理する
  input_string = line;
});
reader.on("close", () => {
  // ここで出力する
  console.log(input_string);
});
```

## 命名規則

- 記号は入れれない($,\_は除く)
- 予約後は使えない
- キャメルケースで書くこと

```javascript
// 例
let tomatoCount;
let tomatoCountNumber;
```

## 演算子

### typeof演算子　データ型を判定する
- コンソール画面で確認できる
```javascript
typeof 3
//=> number
typeof "shohei"
//=> string
typeof { name: "shohei" }
//=> object
typeof [1,2,3]
//=> object
```


### 代入演算子 ++について

- 以下は同じ意味になる
- ただし、引数に使う場合の戻り値は異なる

```javascript
let result = 5;
result = result + 1;
result += 1;
result++;
++result;

// 基本的にはresult += 1;を使うこと
```

### 式代入

- "`"で囲んで ${}の中に javascript をかける

```javascript
string = "hello " + user + " !";
// => hello shohei !

string = `hello ${user} !`;
// => hello shohei !
```

## 改行の仕方

- `\n`を使う方法
- ``（クォート）を使う方法

```javascript
string = "hello\nshohei!";
/* => hello
shohei !`*/
string = `hello
shohei!`;
/* => hello
shohei !`*/
```

## 型変換

### 数値に

```javascript
const userInput = "10.9";
let calcResult;
calcResult = Number(userInput); //小数点に
//=> 10.9
calcResult = parseInt(userInput); //整数に
//=> 10
calcResult = parseFloat(userInput); //小数点に
//=> 10.9
```

### 文字列に

```javascript
const userInput = 10;
let calcResult;
calcResult = String(userInput); 
calcResult = userInput.toString(); 
```

## 真偽値

## 配列
- 配列に値を加える
```javascript
array = [];
array.push("apple");
```

## プロパティについて
### プロパティの設定、変更と追加
```javascript
const coffee = {
  name: "Chocolate Mocha",
  size: 350,
  isHot: true,
  toppings: ["Cinnamon", "Caramel"],
};
console.log(coffee.size);
// => 350

//プロバティ変更の記述
coffee.isHot = false;

//プロバティ追加の記述
coffee.barista = "shohei"; //プロパティにbarista、値に"shohei"を追加
console.log(coffee.barista);
// => shohei
```

## 関数について
### 関数宣言
- 下記では`add`という関数を定義した
```javascript
// 関数宣言
function add() {
  console.log(1 + 1);
}

//関数の呼出
add();
//=> 2
```

### 引数とパラメータ
```javascript
// ()内をパラメータまたは仮引数という
function add(num1,num2) { //()には引数の2,3がそれぞれnum1,num2というパラメータに代入される
  console.log(num1 + num2);
}
//=> 5

//()内を引数またはアーグメントという
add(2,3);
```

