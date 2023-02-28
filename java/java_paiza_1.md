
## 1,000行の整数の入力して1,000行の出力

```java
import java.util.*;

public class Main {

  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);

    // int型の配列aを定義 要素数は1000
    int[] a = new int[1000];

    // 入力値をfor文で配列aに入れる
    for (int i = 0; i < 1000; i++) {
      a[i] = sc.nextInt();
    }

    // 拡張for文で配列全部を出力
    for (int x : a) {
      System.out.println(x);
    }

    sc.close();
  }
}
```

## 1,000個の整数の半角スペース区切りの入力
- まず配列を作成する
- 複数の場合はfor文でその配列に受け取る
- 出力は拡張for文で行う

### Scannerクラスのnextメソッドは空白文字で分けることができる
- splitで分ける必要がない

```java
import java.util.*;
public class Main {
    public static void main(String[] args) {
        
        Scanner sc = new Scanner(System.in);
        int[] array = new int[5];
        
        for (int i = 0; i < 5; i++) {
            array[i] = sc.nextInt();
        }
        
        for ( int a : array){
            System.out.println(a);
        }
    }
    
}
```

## 1 行目で与えられる N 個の整数の入力

```java
import java.util.*;
public class Main {
    public static void main(String[] args) {
        // 自分の得意な言語で
        // Let's チャレンジ！！
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        
        int[] num = new int[n];
        for(int i = 0; i < n; i++) {
            num[i] = sc.nextInt();
        }
        
        for ( int j :  num) {
        System.out.println(j);
        }
    }
}
```

## [1 行目で与えられる N 個の文字列の入力 (large)](https://paiza.jp/works/mondai/stdin_primer/java/stdin_primer__string_number_boss/result?token=feef0cf27f2931be911332cdba74575e)

- Scannerクラスのnextメソッドで勝手に空白文字で分けてくれるのでシンプルに記述できる

```java
import java.util.*;
public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        
        String[] num = new String[n];
        for(int i = 0; i < n; i++) {
            num[i] = sc.next();
        }
        
        for ( String j :  num) {
        System.out.println(j);
        }
    }
}
```

## [文字列と整数の組からの選択](https://paiza.jp/works/mondai/stdin_primer/java/stdin_primer__pair_data_boss/result?token=cc816b3577bd0988a213d70703eb878e)

- 8番目の列を表示
```java
import java.util.*;
public class Main {
    public static void main(String[] args) {
        
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        
        String[] num_1 = new String[n];
        String[] num_2 = new String[n];
        for(int i = 0; i < n; i++) {
            num_1[i] = sc.next();
            num_2[i] = sc.next();
        }
            System.out.println(num_1[7] + " " + num_2[7]);
    
    }
}
```