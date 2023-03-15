# 累積和

- [累積和](#累積和)
  - [累積和の考え方](#累積和の考え方)
  - [開区間と閉区間](#開区間と閉区間)
    - [区間の和 1](#区間の和-1)
    - [区間の和 2](#区間の和-2)
    - [区間の和 3](#区間の和-3)
    - [区間の和 4](#区間の和-4)
    - [連続する N 個の和の最大値](#連続する-n-個の和の最大値)
    - [連続する N 個の和の最大値 2](#連続する-n-個の和の最大値-2)
    - [連続する N 個の和の最大値 3](#連続する-n-個の和の最大値-3)
    - [ 連続する N 個の和の最大値 4](#-連続する-n-個の和の最大値-4)
  - [区間内の個数](#区間内の個数)
    - [区間内の個数 1](#区間内の個数-1)
    - [区間内の個数 3](#区間内の個数-3)
    - [区間内の個数 4](#区間内の個数-4)
  - [区間内の個数 (文字列) 1](#区間内の個数-文字列-1)
    - [区間内の個数 (文字列) 1 ](#区間内の個数-文字列-1-)
    - [区間内の個数 (文字列) 1 ](#区間内の個数-文字列-1--1)
    - [ 区間内の個数 (文字列) 4](#-区間内の個数-文字列-4)
  - [二次元累積和](#二次元累積和)






## 累積和の考え方

```ruby
a_2 から a_7 までの整数を足していけば、累積和を使わずとも答えを求めることができますが、練習として累積和で解いてみましょう。

区間の和を求める方法はいくつかありますが、簡単な方法はループを用いて区間の数を順番に足していくことです。しかしその方法では、区間の長さが長くなるほど、それに比例して計算時間も長くなってしまいます。

そこで、適切な前処理をして累積和を用いることで、答えを求める際の計算時間を大きく短縮することができます。

実際に考えてみましょう。

数列 a_0, a_1, ..., a_(N-1) に対して、数列 s_0, s_1, ... s_N を以下のように考えます。

s_0 = 0
s_1 = a_0
s_2 = a_0 + a_1
s_3 = a_0 + a_1 + a_2
...
s_N = a_0 + a_1 + ... + a_(N-1)

例えば、a = {8, 1, 3} とすると、s = {0, 8, 9, 12} となります。

この数列 s を用いると、a_2 から a_7 までの和は s_8 - s_2 で求めることができます。

実際に考えてみましょう。
s_2 と s_8 はそれぞれ

s_2 = a_0 + a_1
s_8 = a_0 + a_1 + a_2 + s_3 + a_3 + a_4 + a_5 + a_6 + a_7

ですから、s_8 - s_2 は
s_8 - s_2 = (a_0 + a_1 + a_2 + a_3 + a_4 + a_5 + a_6 + a_7) - (a_0 + a_1)
= a_2 + a_3 + a_4 + a_5 + a_6 + a_7

となり、a_2 から a_7 までの和は `s_8 - s_2` で求めることができるとわかります。


このように、数列 a の累積の和をあらかじめ計算しておくことで、長い区間の和でも一回の計算で求めることができます。


また、数列 s の各要素は、以下のように一つ前の要素を用いることで計算できます。

s_0 = 0
s_1 = s_0 + a_0
s_2 = s_1 + a_1
s_3 = s_2 + a_2
...
s_N = s_N-1 + a_N


そして、これを一般化すると
s_(i+1) = s_i + a_i

と考えることができます。これを for 文等ループを用いて実装することで、数列 s の各要素を求めることができます。
```

## 開区間と閉区間

```ruby

累積和の区間は、開区間と閉区間を用いることでよりわかりやすく考えることができます。



閉区間とは、区間の端を含む区間のことで、[2, 7] のように表されます。

例えば、数列 a の範囲を [2, 7] のようにすると、これは

a_2, a_3, a_4, a_5, a_6, a_7

を表します。


開区間とは、区間の端を含まない区間のことで、(2, 7) のように表されます。

例えば、数列 a の範囲を (2, 7) のようにすると、これは

a_3, a_4, a_5, a_6

を表します。


累積和は、左端を閉区間、右端を開区間として考えると理解しやすいです。

このような区間を一般的に半開区間と呼びます。

例えば、数列 a の範囲を [2, 8) としたときの総和を考えてみましょう。

まず、a の範囲を [2, 8) としたとき、これは

a_2, a_3, a_4, a_5, a_6, a_7

を表します。

次に、s_2, s_8 は、a のどこからどこまでの和なのかを考えてみると
s_2 : [0, 2) の総和
s_8 : [0, 8) 総和

となります。

このことから、s_8 から s_2 を引くことで、数列 a の [2, 8) の総和を求めることができるとわかります。

これを、より一般的に考えると
数列 a の範囲を [left, right) としたとき、この範囲の総和は s[right] - s[left] で求めることができる

とすることができます。


最後に、開区間と閉区間の考え方を用いて、今回の問題のように、a_x から a_y (x ≦ y) までの和を求める場合を考えてみましょう。

この場合、範囲の右端は a_y を含むため、数列 a の範囲は [x, y + 1) であると考えることができます。

先ほど説明した通り、数列 a の範囲を [left, right) としたとき、この範囲の総和は s[right] - s[left] で求めることができるため、a_x から a_y までの和は

s[y + 1] - s[x]

と表すことができ、これを用いることでこの問題を解くことができます。
```

### [区間の和 1](https://paiza.jp/works/mondai/prefix_sum_problems/ruby/prefix_sum_problems__section_sum_step1/result?token=94e80bd7c3844556d2c6af1d8f78520e)

```ruby
a = [1, 5, 9, 7, 5, 3, 2, 5, 8, 4]
s = Array.new(11, 0)

(0..8).each do |i|
    s[i + 1] = s[i] + a[i]
end
puts s[8] - s[2]
```

### [区間の和 2](https://paiza.jp/works/mondai/prefix_sum_problems/prefix_sum_problems__section_sum_step2)

```ruby
s = gets.split(" ").map(&:to_i)
a = Array.new(11,0)
(0..11).each do |i|
    a[i+1] = a[i].to_i + s[i].to_i
end
puts a[7+1] - a[2]
```

### [区間の和 3](https://paiza.jp/works/mondai/prefix_sum_problems/prefix_sum_problems__section_sum_step3)

```ruby
x,y = gets.split(" ").map(&:to_i)
s = gets.split(" ").map(&:to_i)
a = Array.new(y+1 , 0)

(0..y).each do |i|
    a[i+1] = a[i] + s[i]
end
puts a[y + 1] - a[x]
```

### [区間の和 4](https://paiza.jp/works/mondai/prefix_sum_problems/prefix_sum_problems__section_sum_boss)

```ruby
n,x, y = gets.split(" ").map(&:to_i)
s = gets.split(" ").map(&:to_i)
a = Array.new(y+1,0)
(0..y).each do |i|
    a[i+1] = a[i] + s[i]
end
puts a[y+1] - a[x]
```

### [連続する N 個の和の最大値](https://paiza.jp/works/mondai/prefix_sum_problems/ruby/prefix_sum_problems__sum_max_step1/result?token=6c9662f1c8a21f95dae2754cf0c7e242)

```ruby
s = %w[1 5 9 7 5 3 2 5 8 4]
s.map!(&:to_i)
max = 0

a =Array.new(s.size+1,0)
(0...s.size).each do |i|
    a[i+1] = a[i] + s[i]
end

(0...a.size - 3).each do |i|
        max = [max, a[i+3] - a[i]].max
end
puts max
```

### [連続する N 個の和の最大値 2](https://paiza.jp/works/mondai/prefix_sum_problems/prefix_sum_problems__sum_max_step2)

```ruby
s = gets.split(" ").map(&:to_i)
max = 0

a =Array.new(s.size+1,0)
(0...s.size).each do |i|
    a[i+1] = a[i] + s[i]
end

(0...a.size - 3).each do |i|
        max = [max, a[i+3] - a[i]].max
end
puts max
```

### [連続する N 個の和の最大値 3](https://paiza.jp/works/mondai/prefix_sum_problems/prefix_sum_problems__sum_max_step3)

```ruby
n = gets.to_i
s = gets.split(" ").map(&:to_i)
max = 0

a =Array.new(n+1,0)
(0...n).each do |i|
    a[i+1] = a[i] + s[i]
end

(0..n - 3).each do |i|
        max = [max, a[i+3] - a[i]].max
end
puts max
```

### [ 連続する N 個の和の最大値 4](https://paiza.jp/works/mondai/prefix_sum_problems/prefix_sum_problems__sum_max_boss)

```ruby
n, k = gets.split(" ").map(&:to_i)
s = gets.split(" ").map(&:to_i)
a = Array.new(n+1,0)

(0...n).each do |i|
    a[i+1] = a[i] + s[i]
end

max = 0
(0..n-k).each do |i|
    max = [max, a[i+k] - a[i]].max
end

puts max
```

## 区間内の個数
---
```
まず、数列 a の各要素が偶数かどうかを格納する数列 b_0, b_1, ..., b_9 を以下のように考えてみます。




0 ≦ i ≦ 9 において
a_i が偶数ならば b_i = 1
a_i が奇数ならば b_i = 0


例えば a = {1, 2, 3, 4, 5} ならば b = {0, 1, 0, 1, 0} となります。



ここで、数列 b の 1 の個数は、数列 a の偶数の個数と同じだとわかります。

つまり、数列 b で累積和を用いて、b_2 から b_7 までの総和を求めればよいです。

b の累積和をとった数列を s とすると、b_2 から b_7 までの総和は、s[8] - s[2] で求めることができます。
```


### [区間内の個数 1](https://paiza.jp/works/mondai/prefix_sum_problems/prefix_sum_problems__section_count_step1)

```ruby
s = %w[1 5 9 7 5 3 2 5 8 4]
s.map!(&:to_i)

a = Array.new(10,0)
b = Array.new(11,0)

(0...10).each do |i|
        a[i] = 1  if s[i].to_i % 2 == 0
end

(0...10).each do |i|
    b[i+1] = b[i] + a[i]
end

p b[8] - b[2]
```

### [区間内の個数 3](https://paiza.jp/works/mondai/prefix_sum_problems/prefix_sum_problems__section_count_step1)

```ruby
x,y = gets.split(" ").map(&:to_i)
s = gets.split(" ").map(&:to_i)

a = Array.new(y+1,0)
b = Array.new(y+2,0)

(0...y+1).each do |i|
        a[i] = 1  if s[i].to_i % 2 == 0
end

(0...y+2).each do |i|
    b[i+1] = b[i].to_i + a[i].to_i
end

p b[y+1] - b[x]
```

### [区間内の個数 4](https://paiza.jp/works/mondai/prefix_sum_problems/prefix_sum_problems__section_count_boss)

```ruby
n,x,y = gets.split(" ").map(&:to_i)
s = gets.split(" ").map(&:to_i)

a = Array.new(y+1,0)
b = Array.new(y+2,0)

(0...y+1).each do |i|
        a[i] = 1  if s[i].to_i % 2 == 0
end

(0...y+2).each do |i|
    b[i+1] = b[i].to_i + a[i].to_i
end

p b[y+1] - b[x]
```

## 区間内の個数 (文字列) 1 

```
文字列 str を "bwwbwbbwbwbb" とします。

文字列 str の 3 文字目から 8 文字目までの 'b' の個数を累積和を用いて求めてください。



(ヒント)

文字列 str の i 文字目を str_i (1 ≦ i ≦ 10) とします。



まず、文字列 str の各要素が 'b' かどうかを格納する数列 b_0, b_1, ..., b_9 を以下のように考えてみます。




1 ≦ i ≦ 10 において
str_i が 'b' ならば b_(i-1) = 1
str_i が 'b' でないならば b_(i-1) = 0


例えば str = "bwbwwbwbwb" ならば b = {1, 0, 1, 0, 0, 1, 0, 1, 0, 1} となります。



ここで、数列 b の 1 の個数は、文字列 str の 'b' の個数と同じだとわかります。

つまり、数列 b で累積和を用いて、b_2 から b_7 までの総和を求めればよいです。

累積和をとった数列を s とすると、b_2 から b_7 までの総和は、s[8] - s[2] で求めることができます。
```

### [区間内の個数 (文字列) 1 ](https://paiza.jp/works/mondai/prefix_sum_problems/prefix_sum_problems__string_count_step1)

```ruby
str = "bwwbwbbwbwbb"
a = Array.new(str.size ,0)
b = Array.new(str.size ,0)

(0..str.size).each do |i|
        a[i] = 1  if str[i] == "b"
end

(0...str.size).each do |i|
    b[i+1] = b[i].to_i + a[i].to_i
end

p b[8] - b[2]
```

### [区間内の個数 (文字列) 1 ](https://paiza.jp/works/mondai/prefix_sum_problems/prefix_sum_problems__string_count_step3)

```ruby
x, y = gets.split(" ").map(&:to_i)
str = gets.chomp

a = Array.new(y+1,0)
b = Array.new(y+2,0)

(0...y).each do |i|
    a[i] = 1 if str[i] == "b"
end

(0..y).each do |i|
    b[i+1] = b[i].to_i + a[i].to_i
end

puts b[y] - b[x-1]
```

### [ 区間内の個数 (文字列) 4](https://paiza.jp/works/mondai/prefix_sum_problems/prefix_sum_problems__string_count_boss)

```ruby
n, x, y = gets.split(" ").map(&:to_i)
str = gets.chomp

a = Array.new(y,0)
b = Array.new(y,0)

(0...y).each do |i|
    a[i] = 1 if str[i] == "b"
end

(0..y).each do |i|
    b[i+1] = b[i].to_i + a[i].to_i
end

puts b[y] - b[x-1]
```


## 二次元累積和

領域の和を求める方法はいくつかありますが、簡単な方法はループを用いて領域内の数を順番に足していくことです。しかしその方法では、領域の大きさが大きくなるほど、それに比例して計算時間も長くなってしまいます。



そこで、適切な前処理をして累積和を用いることで、答えを求める際の計算時間を大きく短縮することができます。



実際に考えてみましょう。

問題で与えられた領域を図示してみます。

'o'が領域内であり、'x'が領域外です。




h 行 w 列の整数の二次元配列 A があったとき、 (h + 1) 行 (w + 1) 列の整数の二次元配列 s の各要素を以下のように考えます。


s_{y, x} =  A[i][j](0 ≦ i < y, 0 ≦ j < x) の和
(0 ≦ y ≦ h, 0 ≦ x ≦ w)

例えば、s_{4, 4} は、以下の領域の整数の和です。

```

       x →
       0 1 2 3 4
y   0  x x x x x
↓   1  x o o o x
    2  x o o o x
    3  x o o o x
    4  x x x x x
```
今回の問題の場合、求めたい和は [1, 4) x [1, 4) の長方形領域内の整数の和 と言うことができます。


また、任意の長方形領域内の整数の和は、4 つの s の足し引きで求めることができます。

ある長方形領域を [sx, gx) × [sy, gy) とすると、この長方形領域内の整数の和は


(長方形領域 [sx, gx) × [sy, gy)  内の整数の和) = s_{gy, gx} - s_{sy, gx} - s_{gy, sx} + s_{sy, sx}

と表すことができます。

特に問題で与えられた領域で考えると以下のようになります。

(長方形領域内の整数の和) = s_{4, 4} - s_{1, 4} - s_{4, 1} + s_{1, 1}

なぜこうなるのか図示して考えてみましょう。

s_{4, 4} は上で示したので、それ以外の三つの領域を以下に示します。


s_{1, 4} は以下の長方形領域内の整数の和です。


```
       x →
       0 1 2 3 4
y   0  o o o o x
↓   1  x x x x x
    2  x x x x x
    3  x x x x x
    4  x x x x x
```

s_{4, 1} は以下の長方形領域内の整数の和です。


```
       x →
       0 1 2 3 4
y   0  o x x x x
↓   1  o x x x x
    2  o x x x x
    3  o x x x x
    4  x x x x x
```

s_{1, 1} は以下の長方形領域内の整数の和です。

```
       x →
       0 1 2 3 4
y   0  o x x x x
↓   1  x x x x x
    2  x x x x x
    3  x x x x x
    4  x x x x x
```

この 4 つの領域を、示した式のように計算すると、一番大きい領域の s_{4, 4} から、要らない領域の s_{1, 4} と s_{4, 1} を引き、二重で引いてしまった s_{1, 1} を足す、ということをしているのがわかります。



また、二次元配列 s の各要素は、この考え方を応用して求めることができます。

s は全て 0 で初期化されているものとすると、s_{x + 1, y + 1} は


`s_{y + 1, x + 1} = s_{y, x + 1} + s_{y + 1, x} - s_{y, x} + A_{y, x}`

と表すことができます。


これによって求まった二次元配列 s を用いて、


`(長方形領域内の整数の和) = s_{gy, gx} - s_{sy, gx} - s_{gy, sx} + s_{sy, sx}`

を用いることで、長方形領域内の整数の和を求めることができます。


### [二次元累積和 1 ](https://paiza.jp/works/mondai/prefix_sum_problems/prefix_sum_problems__2dsection_sum_step1/edit?language_uid=ruby&t=87d40e5ef5745c838d2c8c10b6864214)


```ruby
a = [
    [1, 2, 3, 4, 5],
    [2, 3, 4, 5, 6],
    [3, 4, 5, 6, 7],
    [4, 5, 6, 7, 8],
    [5, 6, 7, 8, 9]
]
s = Array.new(6) { Array.new(6, 0) }

(0..4).each do |i|
  (0..4).each do |j|
    s[i + 1][j + 1] = s[i + 1][j] + s[i][j + 1] - s[i][j] + a[i][j]
  end
end

puts s[4][4] - s[1][4] - s[4][1] + s[1][1]
```