## 文字を出力
```java
public class Main {
    public static void main(String... args) {
        System.out.println("paiza");
    }
}
```
### 改行したくない場合
```java
System.out.print("paiza");
```

### javaプログラムの基本構造
```
クラス {
    メソッド1 {
        ステートメント1
        ステートメント2
    }
    メソッド2 {
        ステートメント3
        ステートメント4
    }
}

```

### インデント
- javaでは改行は半角スペース4つ分

## 変数の宣言
### 変数の型
- 変数を使うとき、最初にデータの種類を指定して宣言する必要がある
```java
String player = "勇者"; // 文字列データの変数
int number = 3; // 整数データの変数
double rand = Math.random() // 小数点以下の数値を扱うことのできる
```
- Stringの頭文字は大文字にします。intは、すべて小文字
- 2回目以降、変数にデータを代入する時には、データの種類の指定は不要

### 文字列と変数の連結
- 変数と文字列は、「+」記号で連結できる
```java
public class Main {
	public static void main(String[] args) {
		String player = "勇者";
		System.out.println(player + "は、レベルアップした");
	}
}
```

```java
// 数の表示とサイコロ
public class Main {
	public static void main(String[] args) {
		double rand = Math.random() * 6 + 1;
		int number = (int)rand;
		System.out.println("サイコロの目は" + number +"です");
	}
}

```

## javaでのif文について
- 基本的にはjavascriptと同じ
```
if (条件式1) {
    処理1;
} else {
    処理2;
}
```