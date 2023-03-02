# stack問題関連まとめ

- [stack問題関連まとめ](#stack問題関連まとめ)
  - [スタック実装編 step 1](#スタック実装編-step-1)
  - [スタック実装編 step 2](#スタック実装編-step-2)
  - [キュー実装編 step 1 ](#キュー実装編-step-1-)




## [スタック実装編 step 1](https://paiza.jp/works/mondai/reviews/show/fa58002cb29af58334396d17350c2af9)

```ruby
n = gets.to_i

# stackの配列を用意
stack = []
n.times do |i|

    # コマンドと値を分けて定義
    command , val = gets.split(" ").map(&:to_i)
    
    # pushならstackに値を加える
    if command == 1
        stack << val
    else
        # popならstackの最後尾の要素を削除
        stack.pop
    end
    puts stack.join(" ")
end
```

## [スタック実装編 step 2](https://paiza.jp/works/mondai/stack_queue/stack_queue__stack_step2/edit?language_uid=ruby)

```ruby
n = gets.to_i

# stackの配列を用意
stack = []
n.times do |i|

    # コマンドと値を分けて定義
    command, a = gets.chomp.split(" ")
    
    # pushならstackに値を加える
    if command == "1"
        stack << a
    else
        puts stack.pop
    end
    puts stack.join(" ")
end
```

## [キュー実装編 step 1 ](https://paiza.jp/works/mondai/stack_queue/stack_queue__queue_step1/edit?language_uid=ruby)

```
Q 個のクエリが与えられます。空の配列 A を用意したあと、 Q 個のクエリに応じて以下の 2 種類の処理をしてください。

・ PUSH X: 配列 A の末尾に X を追加
・ POP: 配列 A の先頭にある要素を削除

各クエリの処理が終わったあと、配列 A の各要素の値を半角スペース区切りで出力してください。
```
```ruby
n = gets.to_i
stack = []
n.times do |i|
    command, a = gets.chomp.split(" ")
    
    if command == "1"
        stack << a
    else
        stack.shift
    end
    puts stack.join(" ")
end
```