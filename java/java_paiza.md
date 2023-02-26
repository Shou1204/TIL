## Java 体験編 1: Java をはじめよう

- [Java 体験編 1: Java をはじめよう](#java-体験編-1-java-をはじめよう)
  - [02:メッセージの表示](#02メッセージの表示)
  - [03:間違いやすいポイント](#03間違いやすいポイント)
  - [04:コメントを書く](#04コメントを書く)
  - [05:数値と文字列の違い](#05数値と文字列の違い)
  - [06:プログラムで計算する](#06プログラムで計算する)
  - [07:変数にデータを入れる](#07変数にデータを入れる)
  - [08:文字列を受け取る](#08文字列を受け取る)
  - [09:整数を受け取る](#09整数を受け取る)
  - [11:条件に一致したら処理を実行する](#11条件に一致したら処理を実行する)
  - [12:条件に合わせて処理を変える](#12条件に合わせて処理を変える)
  - [13:文字列の一致を判定する](#13文字列の一致を判定する)
  - [14:同じ処理を何度も繰り返す](#14同じ処理を何度も繰り返す)
  - [15:複数のデータを受け取る](#15複数のデータを受け取る)
  - [16:複数のデータを分類する](#16複数のデータを分類する)
- [Java 入門編 2:条件によって処理を変えてみよう](#java-入門編-2条件によって処理を変えてみよう)
  - [01:IF 文による条件分岐](#01if-文による条件分岐)
  - [02:複数の条件を組み合わせてみよう](#02複数の条件を組み合わせてみよう)
  - [03:比較演算子で条件分岐してみよう](#03比較演算子で条件分岐してみよう)
  - [04:おみくじを作ってみよう](#04おみくじを作ってみよう)
  - [05:RPG のクリティカルヒットを再現](#05rpg-のクリティカルヒットを再現)
  - [06:西暦から平成何年かを求めてみよう](#06西暦から平成何年かを求めてみよう)
  - [07:【補講】複数の条件を組み合わせてみよう - AND](#07補講複数の条件を組み合わせてみよう---and)
  - [08:【補講】複数の条件を組み合わせてみよう - OR](#08補講複数の条件を組み合わせてみよう---or)
  - [09:【補講】条件の評価結果を理解しよう](#09補講条件の評価結果を理解しよう)
  - [10:【補講】データ型について理解しよう](#10補講データ型について理解しよう)
  - [データ型の変換方法3つ](#データ型の変換方法3つ)
  - [11:【補講】税込み金額を計算する](#11補講税込み金額を計算する)
- [Java入門編3: ループ処理を学ぶ](#java入門編3-ループ処理を学ぶ)
  - [01:条件によるくり返し処理1 - while](#01条件によるくり返し処理1---while)
  - [02:条件によるくり返し処理2 - while](#02条件によるくり返し処理2---while)
  - [03:RPGの攻撃シーンを作る](#03rpgの攻撃シーンを作る)
  - [04:0から4までを表示してみよう - for](#040から4までを表示してみよう---for)
  - [05:繰り返しでHTMLを作成する](#05繰り返しでhtmlを作成する)
  - [06:データの読み込み（標準入力）](#06データの読み込み標準入力)
  - [07:データを読み込んでみよう - 標準入力](#07データを読み込んでみよう---標準入力)
  - [08:複数データを読み込んでみよう](#08複数データを読み込んでみよう)
  - [09:西暦年と平成年の対応表を作る](#09西暦年と平成年の対応表を作る)



### 02:メッセージの表示

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello world");
    }
}
// Hello world
```

### 03:間違いやすいポイント

- 正しいつづり出かけているか
- エラーメッセージをきちんと読むこと

### 04:コメントを書く

```java
// コメントアウト

/* 範囲でコメントアウト
できます */
ここは表示されます

/* これ以降コメントアウト
ここは表示されません
```

### 05:数値と文字列の違い

```java
// 数字は足される
public class Main {
    public static void main(String[] args) {
        System.out.println(100 + 30);
    }
}
// 130

public class Main {
    public static void main(String[] args) {
        System.out.println("100 + 30");
    }
}
// 100 + 30
```

### 06:プログラムで計算する

- 四則演算の話など
- 他の言語と同じ

### 07:変数にデータを入れる

- 命名規則は ruby と変わらない

```java
public class Main {
    public static void main(String[] args) {
        String greeting = "Hello world";
        System.out.println(greeting);    // Hello world
    }
}
```

### 08:文字列を受け取る

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        String text = scan.next();
        System.out.println(text);
    }
}
```

```java
// 入力
// paizaラーニング
// Java体験編

import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        String message = scan.next();
        System.out.println(message);
        message = scan.next();
        System.out.println(message);
    }
}

// 出力
// paizaラーニング
// Java体験編
```

### 09:整数を受け取る

```java
// 数値の受け取り方
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int number = scan.nextInt();
        System.out.println(number);    // 120 -> 120
    }
}

// 文字列と整数をプラス記号で結ぶと、整数データを文字列に自動的に変換してから、連結します。
public class Main {
    public static void main(String[] args) {
        int number = 120;
        System.out.println("おこづかい" + number + "円");    // おこづかい：120円
    }
}
```

### 11:条件に一致したら処理を実行する

```java
if (条件式) {
    // 条件式が真の場合に実行する処理
}
```

### 12:条件に合わせて処理を変える

- else if の間に半角スペースがあるので注意

```java
if (条件式1) {
    // 条件式1が真の場合に実行する処理
} else if (条件式2) {
    // 条件式1が偽で、条件式2が真の場合に実行する処理
} else {
    // 条件式1、2が偽の場合に実行する処理
}
```

### 13:文字列の一致を判定する

Java において文字列を比較する場合には、==演算子を使用することは推奨されません。
==演算子は、参照の比較を行うため、同じ文字列でも参照が異なる場合には、等しくないと判断されるため

```java
String str1 = "Hello";
String str2 = "World";
String str3 = "Hello";

if (str1.equals(str2)) {
    System.out.println("str1とstr2は等しいです");
} else {
    System.out.println("str1とstr2は等しくありません");
}

if (str1.equals(str3)) {
    System.out.println("str1とstr3は等しいです");
} else {
    System.out.println("str1とstr3は等しくありません");
}
```

- ポイント：java では文字列の比較の時は"=="ではなく`equals`を使う

### 14:同じ処理を何度も繰り返す

- for の基本形
- 初期化式: 反復処理の前に最初に 1 回だけ実行される式です。
- 条件式: 反復処理が実行されるかどうかを判断する式です。条件式が true の間は反復処理が繰り返され、false になった時点で反復処理が終了します。
- 更新式: 反復処理が 1 回実行された後に毎回実行される式です。

```java
for (初期化式; 条件式; 更新式) {
    // 反復処理を行う文
}
```

```java
// 1から5までの数字を表示する
for (int i = 1; i <= 5; i++) {
    System.out.println(i);
}
// 出力: 1 2 3 4 5

// 配列の要素を1つずつ表示する
int[] array = {1, 2, 3, 4, 5};
for (int i = 0; i < array.length; i++) {
    System.out.println(array[i]);
}
// 出力: 1 2 3 4 5

// 文字列の各文字を1つずつ表示する
String str = "Hello";
for (int i = 0; i < str.length(); i++) {
    System.out.println(str.charAt(i));
}
// 出力: H e l l o

```

### 15:複数のデータを受け取る

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int count = scan.nextInt();
        System.out.println(count);

        for (int i = 0; i < count; i++) {
            String name = scan.next();
            System.out.println("Hello " + name);
        }
    }
}
```

### 16:複数のデータを分類する

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int count = scan.nextInt();

        for (int i = 0; i < count; i++) {
            int number = scan.nextInt();
            System.out.println(number);

            if (number == 10) {
                System.out.println(number + "は10に等しい");
            } else if (number > 10) {
                System.out.println(number + "は10より大きい");
            } else {
                System.out.println(number + "は10未満");
            }
        }
    }
}
```

## Java 入門編 2:条件によって処理を変えてみよう

### 01:IF 文による条件分岐

```java
// if文による条件分岐
public class Main {
	public static void main(String[] args) {
		int number =((int)(Math.random() * 3 + 1)) * 100;
		System.out.println("あなたの得点は" + number + "ポイントです");
		// ここにif文を追加する
		if (number == 300) {
			System.out.println("おめでとう！");
		} else {
			System.out.println("ざんねん！");
		}
	}
}
```

### 02:複数の条件を組み合わせてみよう

- else if の使い方の復習など

### 03:比較演算子で条件分岐してみよう

- 比較演算子の基本の復習

### 04:おみくじを作ってみよう

- 条件分岐の基本

### 05:RPG のクリティカルヒットを再現

- 再び基本

### 06:西暦から平成何年かを求めてみよう

```
- 西暦年から平成年を求めるには、これとは逆に、西暦年から「1988」を引きます。
- 平成年から西暦年を求めるには、平成年に「1988」を足します
```

### 07:【補講】複数の条件を組み合わせてみよう - AND

```java

条件1 && 条件2

//条件1と条件2の両方が成立した時、全体の条件が成立する
```

### 08:【補講】複数の条件を組み合わせてみよう - OR

```java
条件1 || 条件2

// 条件1と条件2の一方でも成立した時、全体の条件が成立する
```

### 09:【補講】条件の評価結果を理解しよう

- 論理演算とは

```java
Javaでは、「条件が成立したとき」と「成立しなかったとき」といった状態を専用のデータ型で表します。条件が成立したときの状態を「真」または「true」(トゥルー)と呼びます。そして、条件が成立しなかったときの状態を「偽」または「false」(フォールス)と呼びます。

- 条件が成立したとき：真、true
- 条件が成立しなかったとき：偽、false


if文の条件は、論理演算です。たとえば、次のようなな条件は、number変数の値によって、条件が成立したり、成立しなかったりします。

number変数が「1」の場合
- number == 1 true
- number <= 10 true
- number >= 10 false
- number < 10 true
- number > 10 false

number変数が「10」の場合
- number == 1 false
- number <= 10 true
- number >= 10 true
- number < 10 false
- number > 10 false

論理演算は、評価の結果として、trueかfalseを返します。
```

```java
// 条件の評価結果

public class Main {
    public static void main(String[] args) {
        int number = 1;
        boolean flag = number == 1;
        if (flag) {
            System.out.println("スキ！");   //条件が成立したときの処理
        } else {
            System.out.println("キライ");   //条件が成立しなかったときの処理
        }
        System.out.println(flag);
    }
}
```

### 10:【補講】データ型について理解しよう

```java
// データ型の種類

int： 32ビット整数 -2147483648 から2147483647
byte： 8ビット整数 -128から127までの整数
short： 16ビット整数 -32768から32767
long： 64ビット整数 -9223372036854775808から9223372036854775807まで
float：32ビット単精度小数点
double：64ビット倍精度小数点

boolean： 真偽値を扱うためのデータ型です。trueまたはfalseの値を表現できます。
String：文字列を扱うためのデータ型です。文字列を表現するために使用されます。
Array：複数の値を格納するためのデータ型です。
```

### データ型の変換方法3つ
- 自動変換
```java
int a = 10;
double b = a; // aの値は自動的にdouble型に変換される
```

- キャスト
```java
double a = 10.5;
int b = (int)a; // aの値がint型にキャストされる
```

- 文字列型と他のデータ型の変換
```java
String str = "10";
int a = Integer.parseInt(str); // 文字列型をint型に変換する
String b = String.valueOf(a); // int型を文字列型に変換する

Byte.parseByte(): 文字列型をbyte型に変換する
Short.parseShort(): 文字列型をshort型に変換する
Integer.parseInt(): 文字列型をint型に変換する
Long.parseLong(): 文字列型をlong型に変換する
Float.parseFloat(): 文字列型をfloat型に変換する
Double.parseDouble(): 文字列型をdouble型に変換する
```

### 11:【補講】税込み金額を計算する

```java
// エラーが出る
int amount = price / 100.0 * weight;

//原因
Int と指定しているのに小数点以下が出るため

// 対応策
int amount = (int)(price / 100.0 * weight);
//これで()の中が整数に変換されるのでエラーを回避できる
```



## Java入門編3: ループ処理を学ぶ

### 01:条件によるくり返し処理1 - while
- 指定された条件式が true の場合に繰り返し処理を行う
```java
    // カウンタ変数の初期化
while (条件式) {
    // 繰り返し実行したい処理
    // カウンタ変数の更新
}
```

- i が 10 以下の間、i の値を出力し、i の値を 1 ずつ増やしていく
- i が 11 になると、条件式 i <= 10 が false になるため、while 文のループが終了します。
```java
int i = 1; // カウンタ変数の初期化
while (i <= 10) { 
    System.out.println(i); // 繰り返し実行したい処理
    i++; // カウンタ変数の更新
}
```

### 02:条件によるくり返し処理2 - while
- whileの復習
  
### 03:RPGの攻撃シーンを作る
- whileの基本と自己代入演算子の基本

### 04:0から4までを表示してみよう - for
- forの復習

```java
for (初期化式; 条件式; 更新式) {
    // 反復処理を行う文
}
```
```java
// 1から5までの数字を表示する
for (int i = 1; i <= 5; i++) {
    System.out.println(i);
}
// 出力: 1 2 3 4 5

// 配列の要素を1つずつ表示する
int[] array = {1, 2, 3, 4, 5};
for (int i = 0; i < array.length; i++) {
    System.out.println(array[i]);
}
// 出力: 1 2 3 4 5

// 文字列の各文字を1つずつ表示する
String str = "Hello";
for (int i = 0; i < str.length(); i++) {
    System.out.println(str.charAt(i));
}
// 出力: H e l l o
```

### 05:繰り返しでHTMLを作成する

- プルダウンの基本形
```html
<select name='age'>
  <option>1才</option>
  <option>2才</option>
  <option>3才</option>
</select>
```

```java
// 年齢入力のプルダウン作成
public class Main {
    public static void main(String[] args) {
        System.out.println("<select name='age'>");
        for(int i = 1; i <= 10; i++) {
            System.out.println("<option>" + i + "歳</option>");
        }
        System.out.println("</select>");
    }
}
```

### 06:データの読み込み（標準入力）

-  標準入力とは

```
LINUXなどのUnix系OSで用意されていた仕組みです。
標準入力に対応するようにプログラムを作っておけば、プログラム実行時に、ファイルを読み込んだり、キーボードからデータを読み込んだり、パラメータを指定したりというように、入力先を切り替えることができます。
```

### 07:データを読み込んでみよう - 標準入力
- 標準入力で受け取ったデータは数値ではなくテキストになる

```java
// 標準入力
import java.util.*; //標準入力に必要なパッケージをインポート

public class Main {
    public static void main(String[] args) {

        //Scannerクラスでscというインスタンスを作成
        Scanner sc = new Scanner(System.in); 

        // scから入力された整数をnextInt()で読みこむ
        int line = sc.nextInt();
S
        System.out.println(line * 2);
    }
}
```

- 文字列入力、文字列出力の場合

```java
// 標準入力
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // 変数型はStringに！
        String line = sc.next();
        System.out.println(line);
    }
}
```

### 08:複数データを読み込んでみよう

``` java
// 標準入力とループ処理
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String data = sc.next();
        System.out.println("hello " + data);
    }
}
```

```java
// count回の文字列を読み込んでそのまま表示する
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int count = sc.nextInt();

        String line;
        for(int i = 0; i < count; i++) {
            line = sc.next();
            System.out.println(line);
        }
    }
}
```

### 09:西暦年と平成年の対応表を作る

```java
// 西暦年と平成年の対応表を作る
// 1989年から2016年までをループで出力
// ループ内で、各西暦年を平成年に変換

public class Main {
    public static void main(String[] args) {
        int seireki, heisei;
        for (seireki = 1989; seireki <= 2016; seireki++) {
            System.out.print("西暦" + seireki + "年は、");
            heisei = seireki - 1988;
            System.out.println("平成" + heisei + "年です。");
        }
    }
}
```