# 学習の覚書

## 主に paiza で練習問題をこなしての学習メモです。

## 値入力の基本

- 文字列

```ruby
gets.chomp
```

- 数字

```ruby
gets.to_i

# 小数点を含む場合
gets.to_f #.to_iでは整数になる
```

## 配列

### 配列基本

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

### 配列を合計する

```ruby
divisors = [1,2,3]
divisors.sum
# => 6
```

### 配列を抜き出す

`配列[最初に取り出す添字, 取出個数]`

```ruby
array = [1, 2, 3, 4, 5]
first_two = array[0, 2]
puts first_two
#=> 1,2
```

## 配列から最大値、最小値を取り出す

```ruby
[1, 5].min  # => 1
[1, 5].max  # => 5
```

# ruby での用途別メソッド

## 文字列から削除

- 変数以外の文字か判定して、含まれていない文字列を`<<`で result に追加している。

```ruby
vowels = "aiueoAIUEO"
    result = ""
    s.each_char do |char|
        result << char unless vowels.include?(char)
    end
```

## 文字列の置き換え

`文字列のインスタンス.tr("変換したい文字", "置き換え文字")`

```ruby
# 置き換え前	置き換え後
# A	    4
# E	    3
# G	    6
# I	    1
# O	    0
# S	    5
# Z	    2

s = gets.chomp
puts s.tr('AEGIOSZ', '4361052')
```

## 文字列、配列の抜き出し(slice メソッド)

```ruby
#文字列の抜き出し
p "ruby".slice(0)
p "ruby".slice(0,3)
p "ruby".slice(0..3)

# => "r"
# => "rub"
# => "ruby"

# 配列の抜き出し
array = ["Ruby","Python","Java"]
p array[0]
p array.slice(0)
p array[-1]
p array.slice(-1)

# => "ruby"
# => "ruby"
# => "Java"
# => "Java"
```

## 文字列の反転

- `文字列.reverse`

```ruby
p "あいうえお".reverse
# => "おえういあ"
```

## 配列を使う

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

### 約数を抜き出す

```ruby
def divisors(n)
  divisors = []
  (1...n).each do |i|
    divisors << i if n % i == 0
  end
  divisors
end
```

## 分割する

### split メソッド

- 改行（改行は`\n`でもできる。「opt キー」＋「¥」でバックスラッシュ「\」をうてる。）

`文字列.split(区切り文字)`

```ruby
s, t = 'Hello paiza'.split(' ')
puts s
puts t
# 出力例
Hello
paiza
```
