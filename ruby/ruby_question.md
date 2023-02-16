## 以下を出力するコード
```
入力例1
13 5085 2923 8669 3231 7032 73 2683 8317 5545 9774 7179 2646 2470

出力例1
5085
2923
8669
3231
7032
73
2683
8317
5545
9774
7179
2646
2470
```

解答
```ruby
a = gets.split(' ').map(&:to_i)
n = a.shift

a.each { |val| puts val }
```
- 一行の入力なので`split`で全てを個別の数値に分ける。
- 先頭の`13`を除くために`shift`メソッドを使った。配列aからも`13`は取り除かれる。
---

## 以下を出力するコード
```
# 入力例1
5
hello
paiza
813
paiza2020
Nice

# 出力例1
hello
paiza
813
paiza2020
Nice
```

解答
```ruby
n = gets.to_i
a = Array.new(n)
n.times { |i| a[i] = gets.chomp }
a.each { |val| puts val}
```
---

## 文字列と整数を結合して出力する問題
```
# 入力例1
5
paiza 813
pa 81
8pa 13
iza 8
pa 13

# 出力例1
paiza 813
pa 81
8pa 13
iza 8
pa 13
```
解答
```
n = gets.to_i

s = Array.new(n)
a = Array.new(n)
n.times do |i|
  s[i], a[i] =
    gets.split(' ').map.with_index { |val, j| j == 1 ? val.to_i : val }
end

n.times { |i| puts s[i] + ' ' + a[i].to_s }
```
- Enumerator.with_index でインデックスを取得することができる
- 配列.map.with_index で 配列 の要素とインデックスを両方取得しながら繰り返し処理をすることができる
- `条件式 ? a : b` と書くことで、「条件式が真のときは a を返す」、「条件式が負のときは b を返す」という処理ができる
- 上記で、配列 s は文字列を、配列 a は整数を、それぞれ格納するようにできます。
- `a[i]`を文字列に変換しないとエラーになるので注意


## Enumerator.with_index について
- ここの `Enumerator` とは `Enumeratorクラス` のこと。
each や map などがある。
https://docs.ruby-lang.org/ja/latest/class/Enumerator.html

- .with_indexによって番号をつけることができる
ブロック変数の最後に書いた変数がインデックスになる。下記の例だと`index`
```ruby
# 配列arrayにmapメソッドを使う
# with_indexでindexを添える（0から始まる）
array.map.with_index{ |fruit,index|
#処理
}
```

## データ型の理解がなくてエラーが発生した話
- 下記のコードでエラーが発生。
```ruby
# 入力
# 2 3
# 1 2 3
# 8 1 3

m = gets.split(" ").map(&:to_i)
n = m.shift
s = Array.new(n).map{ Array.new(m)}
n.times do |i|
    row = gets.split(" ").map(&:to_i)
    m.times { |j| s[i][j] = row[j]}
end
s.each { |row| puts row.join(" ")}
```
-上記の`m.times { |j| s[i][j] = row[j]}`の部分で
```
Main.rb:7:in `block in <main>': undefined method `times' for [3]:Array (NoMethodError)
```
が発生。
### 原因
- mが配列であった事
- 配列は数値としては扱えない

### どういうことか
- 取り出し方で配列になるか数値になるか異なる
例えば
```ruby
n, m = gets.split(' ').map(&:to_i)
puts "n: #{n}, m: #{m}"
# 出力は n: 2, m: 3 
```
```ruby
m = gets.split(" ").map(&:to_i)
n = m.shift
puts "n: #{n}, m: #{m}"
# 出力は n: 2, m: [3]
```
となる。
つまり数値で取り出すには`shift`を使うべきでは無く、一つ目の例で変数を定義するべきであった。

### ドット絵を表示する（2次配列）
```ruby
enemy_img = [[0,0,1,1,1,1,1,1,1,1,1,1,1,1,0,0],
             [1,1,0,0,0,0,0,0,0,0,0,0,0,0,1,1],
             [1,0,0,1,1,1,0,0,0,1,1,1,0,0,0,1],
             [1,1,0,0,0,0,1,1,0,0,0,0,0,0,1,1],
             [0,1,1,1,1,1,1,1,1,1,1,1,1,1,1,0],
             [0,0,0,1,1,1,0,0,0,0,0,1,1,1,0,0],
             [0,0,0,0,1,1,1,0,0,0,0,0,0,1,1,1]]

enemy_img.each do |line|
    # p line
    line.each do |dot|
        # print dot
        if dot == 1
            print "#"
        else
            print " "
        end
    end
    puts ""
end

# 出力

  ############  
##            ##
#  ###   ###   #
##    ##      ##
 ############## 
   ###     ###  
    ###      ###
```