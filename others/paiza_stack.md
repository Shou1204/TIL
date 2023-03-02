# stack問題関連まとめ

- [stack問題関連まとめ](#stack問題関連まとめ)
  - [スタック実装編 step 1](#スタック実装編-step-1)
  - [スタック実装編 step 2](#スタック実装編-step-2)
  - [キュー実装編 step 1 ](#キュー実装編-step-1-)
  - [キュー実装編 step 2](#キュー実装編-step-2)
  - [2 つのキュー](#2-つのキュー)





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

## [キュー実装編 step 2](https://paiza.jp/works/mondai/stack_queue/stack_queue__queue_step2/edit?language_uid=ruby&t=f5d9d5e7e3811b01b108e615f7a3e0e9)

```
Q 個のクエリが与えられます。空の配列 A を用意したあと、 Q 個のクエリに応じて以下の 2 種類の処理をしてください。

・ PUSH X: 配列 A の末尾に 文字 X を追加
・ POP: 配列 A の先頭にある要素を出力し、削除

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
        puts stack.shift
    end
    puts stack.join(" ")
end
```

## [2 つのキュー](https://paiza.jp/works/mondai/stack_queue/stack_queue__practice_step1/edit?language_uid=ruby)

```
Q 個のクエリが与えられます。 2 つのキューを用意したあと、 Q 個のクエリを順に処理してください。各クエリは、以下の 5 つのいずれかです。

・ PUSH 1 X: 1 つ目のキューに数値 X を追加
・ PUSH 2 X: 2 つ目のキューに数値 X を追加
・ POP 1: 1 つ目のキューの先頭の要素を削除し、その値を出力
・ POP 2: 2 つ目のキューの先頭の要素を削除し、その値を出力
・ SIZE: 1 つ目のキュー、 2 つ目のキューに含まれる要素数をそれぞれ出力
```

```ruby
n = gets.to_i
stack_1 = []
stack_2 = []
n.times do |i|
    command, a, b = gets.chomp.split(" ")
    
    if command == "1"
        stack_1 << b if a == "1"
        stack_2 << b if a == "2"
    elsif command == "2"
        if a == "1"
            puts stack_1.shift
        else
            puts stack_2.shift
        end
    else
        puts "#{stack_1.size} #{stack_2.size}"
    end
end
```