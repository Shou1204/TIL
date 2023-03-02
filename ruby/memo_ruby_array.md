# 配列

- [配列](#配列)
  - [配列基本](#配列基本)
    - [入力数が多い時は配列に値を追加する](#入力数が多い時は配列に値を追加する)
    - [配列の文字列を空白で区切って書く](#配列の文字列を空白で区切って書く)
    - [初めの値と終わりの値で配列を作成できる](#初めの値と終わりの値で配列を作成できる)
  - [追加](#追加)
    - [n番目にxを追加する（insertメソッド)](#n番目にxを追加するinsertメソッド)
    - [同じインデックスの値をたす(便利！)](#同じインデックスの値をたす便利)
    - [末尾](#末尾)
  - [削除](#削除)
    - [要素の中身を指定して削除(delete)](#要素の中身を指定して削除delete)
    - [インデックスを指定して削除(delete at)](#インデックスを指定して削除delete-at)
  - [取得](#取得)
    - [条件で取得(select)](#条件で取得select)
    - [文字列を含んでいるものを取得する(include)](#文字列を含んでいるものを取得するinclude)
    - [積集合で複数の配列に共通しているものを取得する](#積集合で複数の配列に共通しているものを取得する)
    - [合計値を取得(sum)](#合計値を取得sum)
    - [複数の要素の取得](#複数の要素の取得)
    - [配列から最大値、最小値を取得](#配列から最大値最小値を取得)
    - [指定](#指定)
  - [更新](#更新)
    - [指定](#指定-1)
    - [配列の先頭を取り出す(shift)](#配列の先頭を取り出すshift)
    - [配列を分ける(each\_slice)](#配列を分けるeach_slice)
    - [1次配列を2次配列に分ける(each\_slice)](#1次配列を2次配列に分けるeach_slice)
  - [検索・判定](#検索判定)
    - [any?メソッド](#anyメソッド)
    - [範囲に含まれているか判定](#範囲に含まれているか判定)
    - [配列aに配列bが含まれているか判定（all?メソッドとinclude?メソッド）](#配列aに配列bが含まれているか判定allメソッドとincludeメソッド)
  - [配列の並び替え（昇順）](#配列の並び替え昇順)
    - [sort メソッド](#sort-メソッド)
    - [sort\_by で昇順も降順も](#sort_by-で昇順も降順も)
  - [配列の先頭、末尾を削除、追加](#配列の先頭末尾を削除追加)
  - [配列の結合（join) 表示を一列にする場合など](#配列の結合join-表示を一列にする場合など)
  - [二次元配列](#二次元配列)
  - [Array.newメソッドで作成する](#arraynewメソッドで作成する)
  - [loop処理](#loop処理)
    - [](#)
    - [インデックスをつける](#インデックスをつける)
  - [mapで作成](#mapで作成)
  - [配列が一周するとき(配列の最初と最後がつながっている時)](#配列が一周するとき配列の最初と最後がつながっている時)
  - [2次配列を1次配列にする(flattenメソッド)](#2次配列を1次配列にするflattenメソッド)








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

### n番目にxを追加する（insertメソッド)
- 基本形
- 
```ruby
array.insert(a, b)

# a = 挿入したい位置
# b = 追加する要素
```
```ruby
array = [1, 2, 3, 4, 5]
array.insert(2, "hello")
p array #=> [1, 2, "hello", 3, 4, 5]

```


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
### 要素の中身を指定して削除(delete)

```ruby
# 数字を削除
numbers = [1, 2, 3, 4, 5]
numbers.delete(3)
p numbers #=> [1, 2, 4, 5]

# 文字列を削除
fruits = ["apple", "banana", "orange", "apple"]
fruits.delete("apple")
p fruits #=> ["banana", "orange"]

# 2次配列
array = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
array.delete([4, 5, 6])
p array #=> [[1, 2, 3], [7, 8, 9]]
```

### インデックスを指定して削除(delete at)
```ruby
array = ["foo", "bar", "baz"]
array.delete_at(1)
puts array.inspect  #=> ["foo", "baz"]

# 2次配列の場合
array = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
array.delete_at(1)
p array #=> [[1, 2, 3], [7, 8, 9]]
```

## 取得
### 条件で取得(select)
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
### 文字列を含んでいるものを取得する(include)
```ruby
array = ["right","light","erect","elect"]
p array.select{|a| a.include?("ect")}
p array.select{|a| a.include?("ght")}
# => ["erect", "elect"]
# => ["right", "light"]
```
### 積集合で複数の配列に共通しているものを取得する
```ruby
array = [2,3,4,5]
array_2 = [1, 2, 3, 4, 5, 6, 7, 8]

# 共通するものをピックアップする
p array & array_2
#=> [2, 3, 4, 5]
```

### 合計値を取得(sum)

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

### 配列の先頭を取り出す(shift)

- shift メソッド
  先頭を取り出して、取り出した値は配列、ハッシュからはなくなる。

  引数を設定した場合は複数の要素を取り出すことができる

```ruby
# 基本形
配列.shift(n)

# 引数なしの場合
arr = [1,2,3,4,5]
a1 = arr.shift
p a1 # => 1
p arr # => [2,3,4,5]

# 引数あり
fruits = ["apple", "banana", "orange", "mango", "kiwi"]
first_two_fruits = fruits.shift(2)
p first_two_fruits 
#=> ["apple", "banana"]
p fruits
#=> ["orange", "mango", "kiwi"]
```

関連メソッド

- shift メソッド：配列の先頭の要素を取り出す。
- unshift メソッド：配列の先頭の要素に詰め込む。
- pop メソッド：配列の最後尾の要素を取り出す。
- push メソッド：配列の最後尾の要素に詰め込む。



### 配列を分ける(each_slice)

- 指定した要素数になってもあまりを出力するのでエラーは出ない
```ruby
# 基本形
配列.each_slice(n) do |slice|
  # スライスに対する処理
end

# 配列を2つずつの要素に分ける
array = [1, 2, 3, 4, 5, 6, 7]
array.each_slice(2) do |slice|
  p slice
end
# [1, 2]
# [3, 4]
# [5, 6]
# [7]


# ハッシュも分けれる
hash = { "a" => 1, "b" => 2, "c" => 3, "d" => 4, "e" => 5, "f" => 6 }
hash.each_slice(2) do |slice|
  p slice.to_h
end
# {"a"=>1, "b"=>2}
# {"c"=>3, "d"=>4}
# {"e"=>5, "f"=>6}
```

### 1次配列を2次配列に分ける(each_slice)
```ruby
# 配列を2個の要素ずつの2次配列に変換
array = [1, 2, 3, 4, 5, 6, 7]
result = []
array.each_slice(2) do |slice|
  result << slice # 別の配列に移し替える
end
p result

# [[1, 2], [3, 4], [5, 6], [7]]
```






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

### 配列aに配列bが含まれているか判定（all?メソッドとinclude?メソッド）
- all?は、ブロックを使って配列の全ての要素が条件を満たすかどうかを判定するメソッド
```ruby
a = [2, 4, 6, 8, 10]
puts a.all? { |num| num.even? }  # true

b = [1, 3, 5, 7, 9]
puts b.all? { |num| num.even? }  # false
```
```ruby
# bの要素はaに全て含まれているか？を判定する

a = [1, 2, 3, 4, 5]
b = [2, 4, 5]

result = b.all? { |elem| a.include?(elem) }
puts result #=> true
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
- 要素の取得方法
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

### 

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

## 配列が一周するとき(配列の最初と最後がつながっている時)
最初の要素と最後の要素が円形に繋がっている要素を 1 次元配列に格納した場合、それらから連続した K 個を取り出す際は要素数の剰余(インデックスを要素数で割った値)を用いると良い

```ruby
# 0~5 の数字を4から3つ表示

array = [0,1,2,3,4,5]

# 要素の最後と最初が繋がる
(0...3).each do |j|
  p array[(4+j)%6] # 要素数の余剰
end
# =>4 , 5, 0

# 要素の最後を越すと何もないのでnilになってしまう
(0...3).each do |j|
  p array[(4+j)] #通常
end
# =>4 , 5, nil

```

## 2次配列を1次配列にする(flattenメソッド)
`配列.flatten`

2次を1次にする状況としては

- `each_slice`を使用する場合など

```ruby
# 2次配列を1次配列に
array = [1, [2, [3, [4, 5]], 6], 7]
flat_array = array.flatten
p flat_array
# => [1, 2, 3, 4, 5, 6, 7]

# 1次配列に使ってもエラーは出ない
array = [1, 2, 3, 4, 5]
flat_array = array.flatten
p flat_array
# => [1, 2, 3, 4, 5]

# 破壊的メソッドもある
array = [1, [2, [3, [4, 5]], 6], 7]
array.flatten!
p array
# =>[1, 2, 3, 4, 5, 6, 7]
```

