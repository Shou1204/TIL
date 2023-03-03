# stack,q問題関連まとめ

- [stack,q問題関連まとめ](#stackq問題関連まとめ)
  - [スタック実装編 step 1](#スタック実装編-step-1)
  - [スタック実装編 step 2](#スタック実装編-step-2)
  - [キュー実装編 step 1 ](#キュー実装編-step-1-)
  - [キュー実装編 step 2](#キュー実装編-step-2)
  - [2 つのキュー](#2-つのキュー)
  - [最大の区間和 ](#最大の区間和-)
    - [重要：計算量が多いときにスタックかキューを使うとタイムオーバーを回避できることがある](#重要計算量が多いときにスタックかキューを使うとタイムオーバーを回避できることがある)
  - [逆ポーランド記法](#逆ポーランド記法)
  - [括弧列](#括弧列)







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

## [最大の区間和 ](https://paiza.jp/works/mondai/stack_queue/stack_queue__practice_step2/edit?language_uid=ruby&t=cfbf1bc22d5f99185064eab58ddaedd9)

### 重要：計算量が多いときにスタックかキューを使うとタイムオーバーを回避できることがある
- 考え方を覚えておくこと

```N 個の要素からなる数列 A があります。 A に含まれる連続した X 個の要素の和の最大値とその区間の左端の値を出力してください。ただし、要素の和の最大となる区間が複数ある場合はそのうちもっとも先頭の値を出力してください。
たとえば、 N = 4 , A = [2, 3, 4, 1] , X = 2 とします。連続した 2 個の要素の和が最大となる区間は A の 2 番目から 3 番目まで( 3 + 4 = 7 が最大値 )なので、最大値 7 とその区間の左端の値 3 を出力します。
```
```ruby
n, x = gets.chomp.split.map(&:to_i)
num = gets.chomp.split.map(&:to_i)

left_num = num[0] # 区間の和が最大になる左端の値
tmp_sum = 0 # 区間の和

# 区間の和
(0...x).each do |i|
  tmp_sum += num[i]
end
max_sum = tmp_sum # 最初の区間最大値

# チューブの左端を一つ押し出したら、右端から一つ入ってくるイメージ
(0...n-x).each do |i|
    # 左端を引く
    tmp_sum -= num[i]
    # 右端にたす
    tmp_sum += num[i+x]
    
  if tmp_sum > max_sum
    # 左端の数
    left_num = num[i+1]
    max_sum = tmp_sum
  end
end

puts "#{max_sum} #{left_num}"
```

## [逆ポーランド記法](https://paiza.jp/works/mondai/stack_queue/stack_queue__practice_step3/edit?language_uid=ruby&t=13f4728929031cff9479f37d4bbbd995)

```
逆ポーランド記法 で書かれた数式が与えられます。
この数式を計算した結果を出力してください。
この問題は少し難しいですが、スタックを用いて解いてみましょう。
```
```ruby
n = gets.chomp.to_i
a = gets.chomp.split

# stackの入れ物を作成
st = []

# 数式を１文字ずつ判定
(0...n).each do |i|
  # 記号だった場合、1つ前と2つ前の数字を取り出す
  if a[i] == "+" || a[i] == "-"
    num1 = st.pop().to_i
    num2 = st.pop().to_i
    # 1つ前と2つ前の数字を足して、格納し直す
    if a[i] == "+"
      st.push(num1 + num2)
    # 1つ前から2つ前の数字を引いて、格納し直す
    else
      st.push(num2 - num1)
    end
  # 数字だった場合、そのまま格納する
  else
    st.push(a[i].to_i)
  end
end
# stackを表示する
# 正しく作動していれば、数字は一つ
puts st
```

## [括弧列](https://paiza.jp/works/mondai/stack_queue/stack_queue__practice_step4/edit?language_uid=ruby&t=b0bb4113d73b8fcf150f9fd75ee68758)

```
N 文字の 括弧列 S が与えられます。与えられた 括弧列 が 正しい括弧列 かどうか判定してください。

ここで、 括弧列 とは以下のように定義します。

* ( または ) または空文字のみで構成される文字列

また、 正しい括弧列 とは以下のように定義します。

1. 空文字列は正しい括弧列である。
2. 文字列 s が正しい括弧列であるとき、 ( + s + ) は正しい括弧列である。
3. 文字列 s , t が正しい括弧列であるとき、 s + t は正しい括弧列である。
```

- "(" と ")" が揃った時点で配列から値が消えていく
- stackから値が消えたなら正しい組み合わせであるということ
```ruby
n = gets.to_i
s = gets.chomp

st = []

(0...n).each do |i|
  # 配列に値が入っていて、最後の値が"(" 、s[i]が")"の場合
  if st.length > 0 && st[-1] == "(" && s[i] == ")"
    # 最後の値を削除
    st.pop
  # 当てはまらなければ追加
  else
    st.push(s[i])
  end
end

# 値が配列に残っていれば括弧が足りないということ
if st.length == 0
  puts "Yes"
else
  puts "No"
end
```