# 配列

- [配列](#配列)
  - [配列基本](#配列基本)
    - [入力数が多い時は配列に値を追加する](#入力数が多い時は配列に値を追加する)
    - [配列の文字列を空白で区切って書く](#配列の文字列を空白で区切って書く)
    - [初めの値と終わりの値で配列を作成できる](#初めの値と終わりの値で配列を作成できる)
  - [追加](#追加)
    - [同じインデックスの値をたす(便利！)](#同じインデックスの値をたす便利)
    - [末尾](#末尾)
  - [削除](#削除)
    - [条件で削除](#条件で削除)
  - [取得](#取得)
    - [条件で取得](#条件で取得)
    - [合計値を取得](#合計値を取得)
    - [複数の要素の取得](#複数の要素の取得)
    - [配列から最大値、最小値を取得](#配列から最大値最小値を取得)
    - [指定](#指定)
  - [更新](#更新)
    - [指定](#指定-1)
    - [配列の先頭を取り出す](#配列の先頭を取り出す)
  - [検索・判定](#検索判定)
    - [any?メソッド](#anyメソッド)
    - [範囲に含まれているか判定](#範囲に含まれているか判定)
  - [配列の並び替え（昇順）](#配列の並び替え昇順)
    - [sort メソッド](#sort-メソッド)
    - [sort\_by で昇順も降順も](#sort_by-で昇順も降順も)
  - [配列の先頭、末尾を削除、追加](#配列の先頭末尾を削除追加)
  - [配列の結合（join) 表示を一列にする場合など](#配列の結合join-表示を一列にする場合など)
  - [二次元配列](#二次元配列)
  - [Array.newメソッドで作成する](#arraynewメソッドで作成する)
  - [loop処理](#loop処理)
    - [インデックスをつける](#インデックスをつける)
  - [mapで作成](#mapで作成)



## 配列基本

- 追加と置き換えに注意

```ruby
array = Array.new(3) # 3個の配列を作成
# 配列に追加
array << 5 #配列の最後に5を追加する
# => "", "", "", 5
# 配列を置き換え
array[0] = 5 #添字が0なので配列の一つ目を5に置き換える
# => 5, "", ""
```


- 長さ n の配列を生成することができる

```ruby
Array.new(n)
```

- １０回入力して 10 回 puts するプログラム。
- 入力をからの`input`に配列として保持して、`each do`で一つずつ出力している。

```ruby
input = []
10.times do
    input << gets
end

input.each do |i|
    puts i
end
```

- 配列から文字列の変換（joinメソッド）
```ruby
string = ["B"]
p string
# => ["B"]

string = ["B"].join
p string
# => "B"

array_3 = ["alice"]
p array_3.join
# => "alice"

```

### 入力数が多い時は配列に値を追加する

- 例.1000 個の値を入力し、1000 個の値を出力
  Array.new()で配列を取得し、その中に値を入力する。

```ruby
a = Array.new(1000)
1000.times do |i|
    a[i] = gets.to_i
end
a.each do |b|
    puts b
end
```

### 配列の文字列を空白で区切って書く

- `%w`を配列の前に書くと空白区切りで配列を表すことができる

```ruby
# 以下は全く同じもの

array = %w[HND NRT KIX NGO NGO]

array = ["HND", "NRT", "KIX", "NGO", "NGO"]
```

### 初めの値と終わりの値で配列を作成できる
```ruby
array_2 = (1..8).to_a
p array_2
#=> [1, 2, 3, 4, 5, 6, 7, 8]

array_3 = ("a".."d").to_a
p array_3
#=> ["a", "b", "c", "d"]
```


## 追加
### 同じインデックスの値をたす(便利！)
```ruby

# [[0, 200], [1, 240], [0, 120], [3, 460], [1, 240], [2, 3200]]
n.times do
  t, p = gets.split.map(&:to_i)
  sum[t] += p
end
# => [320, 480, 3200, 460]
```
- 好きな位置に挿入する（insertメソッド）
```ruby
配列.insert(挿入位置, 挿入する要素)
```
```ruby
a = [1, 2, 3]
a.insert(2, 4) # 第一引数の位置に第二引数を挿入する
print a # [1, 2, 4, 3]

a = [1, 2, 3]
a.insert(-2, 4) #第一引数をマイナスにすると末尾から数える
print a # [1, 4, 2, 3]

a = [1, 2, 3]
a.insert(2, 4, 5) #第二引数以降に記述すれば挿入する要素を増やせる
print a # [1, 2, 4, 5, 3]
```

- 要素を先頭に挿入（unshiftメソッド）
```ruby
配列.unshift(挿入する要素)
```
```ruby
a = [1, 2, 3]
a.unshift(4)
print a # [4, 1, 2, 3]
```
### 末尾

- push メソッド

```ruby
team = []
team.push("勇者")
```

## 削除
### 条件で削除
- delete_at メソッド

```ruby
team = ["勇者","魔法使い"]
team.delete_at(0)
```

## 取得
### 条件で取得
- select do で条件を指定して取得する
- selectの反対の作用をするrejectがある
```ruby
配列オブジェクト.select { |変数| ブロック処理 }
```
```ruby
array = [1,2,3,4,5]
p array.select { |num| num > 3 }
#=> [4, 5]
```
- each_with_indexを同時に使用できる
```ruby
array = [8,33,43,56,77]
p array.each_with_index.select {|num,index| index > 2}
#=> [[56, 3], [77, 4]]
```
- 文字列を含んでいるものを取得する
```ruby
array = ["right","light","erect","elect"]
p array.select{|a| a.include?("ect")}
p array.select{|a| a.include?("ght")}
# => ["erect", "elect"]
# => ["right", "light"]
```
- 積集合で複数の配列に共通しているものを取得する
```ruby
array = [2,3,4,5]
array_2 = [1, 2, 3, 4, 5, 6, 7, 8]

# 共通するものをピックアップする
p array & array_2
#=> [2, 3, 4, 5]
```

### 合計値を取得

```ruby
divisors = [1,2,3]
divisors.sum
# => 6

array = [1, 3, 5, 6, 3, 2, 5, 23, 2]
ans = 0
array.each { |element| ans += element }
puts ans
```

### 複数の要素の取得
- `配列[最初に取り出す添字, 取出個数]`

```ruby
array = [1, 2, 3, 4, 5]
first_two = array[0, 2]
puts first_two
#=> 1,2
```

### 配列から最大値、最小値を取得

```ruby
[1, 5].min  # => 1
[1, 5].max  # => 5
```

### 指定



## 更新
- mapメソッドで更新する
```ruby
results２ = numbers.map do |item|
    item * 10
end
p results2
```

### 指定

```ruby
team = ["勇者","魔法使い"]
team[0] = "ドラゴン"
```

### 配列の先頭を取り出す

- shift メソッド
  先頭を取り出して、取り出した値は配列、ハッシュからはなくなる。

```ruby
# 配列作成します。
arr = [1,2,3,4,5]
# shift メソッドで先頭の要素を取り出します。
a1 = arr.shift
# 取り出した要素を表示します。
p a1 # => 1
# 配列の残りを表示します。先頭の要素が取り出されていることを確認しましょう。
p arr # => [2,3,4,5]
```

関連メソッド

- shift メソッド：配列の先頭の要素を取り出す。
- unshift メソッド：配列の先頭の要素に詰め込む。
- pop メソッド：配列の最後尾の要素を取り出す。
- push メソッド：配列の最後尾の要素に詰め込む。


## 検索・判定
### any?メソッド 
```ruby
各要素に対する判定条件を使う例
 
p [nil, false].any? #全ての要素が偽なのでfalseが返る
# => false

p [10, nil, false].any? # #10は真なのでtrueが返る
# => true

nums = [ 1, 3, 6 ]
p nums.any? { |val| val > 5 }
# => true
```

### 範囲に含まれているか判定
- include?メソッド
- include?メソッドは文字列にも使えるが、機能が異なるので注意！
```ruby
配列オブジェクト.include?(値)
```
```ruby
puts ["h", "e", "llo"].include?("llo") #=> true
puts ["h", "e", "llo"].include?("hell") #=> false
```


## 配列の並び替え（昇順）

### sort メソッド

- 降順の場合は`reverse`メソッドと組み合わせる

```ruby
array = [300, 200, 150, 400, 100]

array.sort
p array
# => [300, 200, 150, 400, 100]

array.sort.reverse
p array
# => [300, 200, 150, 400, 100]

array.sort!
p array
# =>[100, 150, 200, 300, 400]

array = [  {"name" => "うどん", "price" => "300"},  {"name" => "パスタ", "price" => "700"},  {"name" => "ラーメン", "price" => "500"}]
p array.sort_by {|x| x["price"] }

# => [{"name"=>"うどん", "price"=>"300"}, {"name"=>"ラーメン", "price"=>"500"}, {"name"=>"パスタ", "price"=>"700"}]
```

### sort_by で昇順も降順も

```ruby
a = {リンゴ: 100, バナナ: 800, イチゴ: 300}
puts a.sort_by { |x,y| y}
#=> リンゴ 100 イチゴ 300 バナナ 800

puts a.sort_by { |x,y| -y}  # -をつける
#=> バナナ 800 イチゴ 300 リンゴ 100
```

## 配列の先頭、末尾を削除、追加

```ruby
# unshift
a = [1, 2, 3]
b = a.unshift 0
p a #[0, 1, 2, 3]
p b #[0, 1, 2, 3]

# shift
a = [1, 2, 3]
b = a.shift
p a #[2, 3]
p b #1

# pop
a = [1, 2, 3]
b = a.pop
p a #[1, 2]
p b #3

# push
a = [1, 2, 3]
b = a.push 4
p a #[1, 2, 3, 4]
p b #[1, 2, 3, 4]

# <<
a = [1, 2, 3]
b = a << 4
p a #[1, 2, 3, 4]
p b #[1, 2, 3, 4]
```

## 配列の結合（join) 表示を一列にする場合など

```ruby
array = ['ruby', 'python']
p array.join
# => "rubypython"

array = [['ruby','rails'],['python','django']]
p array.join(' ')
# => "ruby rails python django"
```

## 二次元配列

```ruby
team_c = ["勇者", "戦士", "魔法使い"]
team_d = ["盗賊", "忍者", "商人"]
team_e = ["スライム", "ドラゴン", "魔王"]
teams = [team_c, team_d, team_e]
p teams
# => [["勇者", "戦士", "魔法使い"], ["盗賊", "忍者", "商人"], ["スライム", "ドラゴン", "魔王"]]

p teams[0]
# => ["勇者", "戦士", "魔法使い"]

p teams[0][0]
# => "勇者"

p teams[0][1]
# => "戦士"

p teams[0][2]
# => "魔法使い"
```

## Array.newメソッドで作成する
```ruby
numbers3 = Array.new(4)
p numbers3
# => [nil, nil, nil, nil]

# ４個の配列を作る、中身は1
numbers3 = Array.new(4,1)
p numbers3
# => [1, 1, 1, 1]
```

## loop処理

### インデックスをつける
- `each_with_index`メソッド
```ruby
team = ["勇者", "戦士", "魔法使い"]
team.each_with_index do |person, i|
    puts "#{i}番目の#{person}が、スライムと戦った"
end
```

## mapで作成
```ruby
numbers3 = Array.new(4).map{Array.new(3, 1)}
p numbers3
# => [[1, 1, 1], [1, 1, 1], [1, 1, 1], [1, 1, 1]]
```

