## Java体験編1: Javaをはじめよう

- [java 体験編](#java体験編)
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