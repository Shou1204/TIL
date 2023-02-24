- [学習の覚書](#学習の覚書)
  - [値入力の基本](#値入力の基本)
- [文字列](#文字列)
  - [文字列から削除](#文字列から削除)
  - [文字列の置き換え](#文字列の置き換え)
  - [文字列、配列の抜き出し(slice メソッド)](#文字列配列の抜き出しslice-メソッド)
  - [文字列の反転](#文字列の反転)
    - [約数を抜き出す](#約数を抜き出す)
  - [分割する](#分割する)
    - [split メソッド](#split-メソッド)
  - [小文字、大文字に変換](#小文字大文字に変換)
  - [当てはまるものを数える(count)](#当てはまるものを数えるcount)
  - [演算子](#演算子)
    - [".."と"..."は異なる](#とは異なる)
    - [文字列を一文字ずつ抜き出して繰り返す（each\_char メソッド）](#文字列を一文字ずつ抜き出して繰り返すeach_char-メソッド)
- [表示](#表示)
  - [puts と　 print 　の違い](#puts-と-print-の違い)
- [演算子](#演算子-1)
    - [条件演算子](#条件演算子)


# 学習の覚書

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

---

# 文字列

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

## 小文字、大文字に変換

- downcase で大文字を小文字に変換
- upcase で小文字を大文字に変換
- swapcase で小文字 ⇔ 大文字の変換
- capitalize で先頭の小文字を大文字に変換

## 当てはまるものを数える(count)

- 配列も文字列も数えることができる

```ruby
num =[1,1,2,3,4,4,4]
puts num.count(4)
#result => 3

string = "ある道を通り過ぎた道端さん"
puts string.count("道")

#result => 2
```

## 演算子

### ".."と"..."は異なる

".." は範囲オブジェクトを表す演算子で、指定された範囲内の整数のリストを生成します。例えば、1..10 は 1 から 10 までの整数を含む配列を生成します。

一方、"..." は範囲オブジェクトを表す演算子で、指定された範囲外の整数を生成することができます。例えば、1...10 は 1 から 9 までの整数を含む配列を生成します。

### 文字列を一文字ずつ抜き出して繰り返す（each_char メソッド）

- with_index メソッドと組み合わせることもできる
- 文字列限定

```ruby
"hello世界".each_char {|c| print c, ' ' }
# => h e l l o 世 界

"hello世界".each_char.with_index do |c,i|
  print c," "
end
# => h e l l o 世 界
```

# 表示

## puts と　 print 　の違い

- puts
- print

puts は　改行あり
print は　改行なし

# 演算子

### 条件演算子

```ruby
条件式 ? 式1 : 式2
```

この演算子の意味は、条件式が真であれば 式 1 を評価し、偽であれば 式 2 を評価する、というものです。

```ruby
result = 80
flag = result > 60 ? "合格" : "不合格"
p flag
# => "合格"

# 同じコードをifで書く
result = 80
if result > 60 then
  flag = "合格"
else
  flag = "不合格"
end
p flag
# => "合格"
```
- コードを短く書くことができる

# 値の変換(formatメソッド)
- かなり応用が効いて奥が深い
- 知っていると考えつくロジックが広がるので要学習！
```ruby
# 基本形
format(フォーマット文字列, 引数1, 引数2, ...)

a = 123
b = "abc"
formatted_string = format("a: %d, b: %s", a, b)
puts formatted_string #=> a: 123, b: abc
```

```
%s: 文字列を表します。
%d: 整数を表します。
%f: 浮動小数点数を表します。
%b: 2進数表記で整数を表します。
%e: 指数表記で浮動小数点数を表します。
%x: 16進数表記で整数を表します。
%X: 大文字の16進数表記で整数を表します。
%o: 8進数表記で整数を表します。


p format("%sさんの年齢は%d歳です。", "山田", 30)
#=> "山田さんの年齢は30歳です。"

p format("円周率は%fです。", 3.1415926535)
#=> "円周率は3.141593です。"

p format("2の10乗は%eです。", 2 ** 10)
#=> "2の10乗は1.024000e+03です。"

p format("255の16進数表記は%xです。", 255)
#=> "255の16進数表記はffです。"

p format("7の2進数表記は%bです。", 7)
#=> "7の2進数表記は111です。"
```

## 数字一桁を二桁にする( 3 , 4 =>  03 , 04 )

%02dの部分で2桁の表示を指定

%dは整数値を表す指定子で`%02d`は「最低2桁の表示を行い、足りない場合は0で埋める」という意味
```ruby
hour = 3
minute = 10
result = format("%02d:%02d", hour, minute)
puts result
# => "03:10"

# ３桁の場合
number = 7
result = format("%03d", number)
puts result
# => "007"

# 元が文字列だった場合
str = "abc"
result = format("%05s", str) # "d" が "s" になっている
puts result
# => "00abc"

```