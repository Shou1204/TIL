

## java体験編
### #02:メッセージの表示
```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello world");
    }
}
// Hello world
```

### ＃03:間違いやすいポイント
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
