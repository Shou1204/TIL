### C104:虫食い算
https://paiza.jp/works/challenges/512/page/result
```ruby
def solve(a, b)
  (1..9).each do |x|
    (0..9).each do |y|
      if (x * 10 + y) * y == a * 100 + x * 10 + b
        return puts "#{x} #{y}"
        break
      end
    end
  end
  puts "No"
end

a, b = gets.split.map(&:to_i)
solve(a, b)
```
### C048:タダ飲みコーヒー
https://paiza.jp/works/challenges/225/page/result

```ruby
price,discount = gets.split(" ").map(&:to_i)

total = price
while price > 0
    price = (price * (100 - discount) / 100).to_i
    total += price
end

puts total
```
### [五目並べ（斜め） (paizaランク C 相当)](https://paiza.jp/works/mondai/prob60/tic_tac_toe_4/edit?language_uid=ruby&t=5a8f61ec9ec58dbf3c4586094039aff3)

```ruby
gomoku = []
5.times {|i| gomoku << gets.chomp.split("")}
result = "D"
x = 0
o = 0
(0..4).each do |i|
    if gomoku[i][i] == "X"
        x += 1
    elsif gomoku[i][i] == "O"
        o += 1
    end
    if x == 5
       result = gomoku[2][2]
       break
    elsif o == 5
        result = gomoku[2][2]
        break
    end
end
j = 4
x = 0
o = 0
(0..4).each do |i|
    if gomoku[i][j] == "X"
        x += 1
    elsif gomoku[i][j] == "O"
        o += 1
    end
    j -= 1
    if x == 5
       result = gomoku[2][2]
       break
    elsif o == 5
        result = gomoku[2][2]
        break
    end
end
puts result
```


### [C083:売上の発表](https://paiza.jp/works/challenges/399/page/result)
```ruby
n,r = gets.split(" ").map(&:to_i)
profit = []
n.times do |i|
    profit << (gets.to_i / r)
end
max = profit.max
n.times do |i|
    puts "#{i+1}:" + ("*" *profit[i]) + ("." * (max - profit[i]))
end
```

### [C039:古代の数式](https://paiza.jp/works/challenges/177/page/result)
```ruby
s = gets.chomp
n = s.count("+") + 1
r = s.split("+")
total = 0
n.times do |i|
    count1 = r[i].count("/")
    count10 = r[i].count("<")
    total += count10 * 10 + count1
end
puts total
```

### [C056:テストの採点](https://paiza.jp/works/challenges/266/page/result)
```ruby
n,passing_score = gets.split(" ").map(&:to_i)
# 学生の成績を格納するハッシュ
scores = {}

# 成績を計算する
n.times do |i|
  score_data = gets.split.map(&:to_i)
  test_score = score_data[0]
  absence_count = score_data[1]
  score = [test_score - absence_count * 5, 0].max
  scores[i+1] = score
end

# 合格点以上の学生を出力する
scores.select { |k, v| v >= passing_score }.each_key { |k| puts k }
```

### [辞書 (paizaランク C 相当)](https://paiza.jp/works/mondai/c_rank_level_up_problems/c_rank_dictionary_boss/edit?language_uid=ruby&t=abf3639095f136de8c8753e3fc50a496)
p 人のグループ A , q 人のグループ B , r 人のグループ C があります。各グループのメンバーにはそれぞれ番号がつけられており、 A グループの i 番目の人は B グループの j 番目の人に仕事を任せ、 B グループの j 番目の人は与えられた仕事を C グループの k 番目の人に任せます。すると結局、 A グループの i 番目の人の仕事をするのは C グループの k 番目の人だということになります。

パイザ君は A グループの各人の仕事を結局 C グループの誰が行うことになるのか知りたがっています。 A グループの人のそれぞれが最終的に C グループの誰に仕事を頼むことになるのかを、 A グループの人の番号が小さい順に p 行出力してください。


```ruby
a,b,c = gets.split(" ").map(&:to_i)
ab = {}
bc = {}
a.times do
    key,value = gets.split(" ").map(&:to_i)
    ab[key] = value
end
b.times do
    key,value = gets.split(" ").map(&:to_i)
    bc[key] = value
end
ab = ab.sort_by{|x,y| x}.to_h
j = 1
ab.each_value do |i|
    puts "#{j} #{bc[i]}"
    j += 1
end
```

### [シミュレーション (paizaランク C 相当)](https://paiza.jp/works/mondai/c_rank_level_up_problems/c_rank_simulation_boss/edit?language_uid=ruby&t=06ef4c709101829f4231b032f542821a)
カウンター魔法を得意とするパイザ君は、同じくカウンター魔法を使うモンスターと戦っています。バトルはターン制で、パイザ君が先攻で、パイザ君とモンスターで交互に魔法を使い合います。パイザ君の魔法は 1 回目と 2 回目に使うときにはダメージ 1 ですが、 3 回目以降の n 回目には、(モンスターから受けた (n - 1) 回目の攻撃のダメージ) + (モンスターから受けた (n - 2) 回目の攻撃のダメージ) のダメージを与えます。モンスターの魔法はこれよりも強力で、 1 回目と 2 回目には同じくダメージ 1 ですが、 3 回目以降の n 回目には、 (パイザ君から受けた (n - 1) 回目の攻撃のダメージ) * 2 + (パイザ君から受けた (n - 2) 回目の攻撃のダメージ) のダメージを与えます。

パイザ君は自分がどれくらいモンスターの攻撃を耐えられるか知りたいと思っています。パイザ君の体力を H として、両者が同じ魔法を使い続けたとき、モンスターの何回目の攻撃でパイザ君の体力が 0 以下になるかを出力してください。

- 入力例
7

- 出力例
4

```ruby
h = gets.to_i
paiza_a = 1
paiza_as={1 => 1,2 => 1}
enemy_a = 1
enemy_as={1 => 1,2 => 1}
count = 0
2.times do |i|
    if h > 0
        h -= 1
        count += 1
    end
end
puts count if h <= 0

(3..100).each do |i|
        paiza_a = enemy_as[i-1] + enemy_as[i-2]
        paiza_as[i] = paiza_a
        enemy_a = (paiza_as[i-1]) * 2 + paiza_as[i-2]
        enemy_as[i] = enemy_a
        h -= enemy_a
        count +=1
        break if h <= 0
end
puts count
```

### [C060:辞書の作成 再チャレンジ採点結果](https://paiza.jp/challenges/291/retry_result/b7b8106a784a5d8d1227ce8e4b61c062)

```ruby
n,k,page = gets.split(" ").map(&:to_i)
words = gets.chomp.split(" ")
words = words.sort_by{|x| x }

words_number = k * (page-1)
((words_number)..(words_number + (k-1))).each do |i|
    puts words[i]
end
```

### [五目並べ（縦） Ruby編」](https://paiza.jp/works/mondai/prob60/tic_tac_toe_3/edit?language_uid=ruby)
```ruby
a =[]
5.times {|i| a << gets.chomp.split("")}
w = %w[X O]
w.each do |xo|
    (0..4).each do |i|
    count = 0
        a.each do |j|
            if j[i] == xo
                count += 1
            end
        end
    return puts xo if count == 5
    end
end
puts "D"
```

### [五目並べ（斜め）](https://paiza.jp/works/mondai/prob60/ruby/tic_tac_toe_4/result?token=f35ed54e40cb9406695c1e9efcdb8169)

```ruby
a =[]
5.times {|i| a << gets.chomp.split("")}
w = %w[X O]
w.each do |xo|
count = 0
j = 0
    a.each do |i|
        if i[j] == xo
                count += 1
        end
        j += 1
    return puts xo if count == 5
    end
end
w.each do |xo|
count = 0
j = 4
    a.each do |i|
        if i[j] == xo
                count += 1
        end
        j -= 1
    return puts xo if count == 5
    end
end
puts "D"
```

### [五目並べ Ruby編](https://paiza.jp/works/mondai/prob60/ruby/tic_tac_toe_9/result?token=d0d180d6a78844eccf0c3571f902b498)

```ruby
def yoko(a,xo)
    xo.each do |x|
        a.each do |i|
           if i.count(x) == 5
               return puts x
            end
        end
    end
    tate(a,xo)
end

def tate(a,xo)
    xo.each do |x|
        (0..4).each do |i|
        count = 0
          (0..4).each do |j|
           if a[j][i] == x
               count += 1
               return puts x if count == 5
            end
          end
        end
    end
    naname(a,xo)
end

def naname(a,xo)
    xo.each do |x|
        count = 0
        j = 0
        (0..4).each do |i|
            if a[i][j] == x
                count += 1
                return puts x if count == 5
                j += 1
            end
        end
    end
    xo.each do |x|
        count = 0
        j = 4
        (0..4).each do |i|
            if a[i][j] == x
                count += 1
                return puts x if count == 5
                j -= 1
            end
        end
    end
    puts "D"
end

a =[]
5.times {|i| a << gets.chomp.split("")}
xo = %w[X O]
count = 0

yoko(a,xo)
```

### [1人の占い結果 Ruby編](https://paiza.jp/works/mondai/prob60/ruby/fortune_telling_4/result?token=83111a3d0c7097467c1fd15739849e10)

```ruby
target = gets.chomp
n = gets.to_i
data_1 = {}
n.times do |i|
    name, status_1 = gets.chomp.split(" ")
    data_1[name] = status_1
end

data_2 = {}
n = gets.to_i
n.times do |i|
    status_1 , status_2 = gets.chomp.split(" ")
    data_2[status_1] = status_2
end

target_status_1 = data_1.select {|x,y| x == target}.values

target_status_2 = []
data_1.each_value do |i|
    target_status_2 = data_2.select {|x,y| x == target_status_1.join}.values
end

puts target_status_2
```
- selectで抽出した値は配列なので`.join`で文字列に変換している
- each_valueの中はスコープ範囲外なので先に変数の宣言をしておくこと

### [占い Ruby編](https://paiza.jp/works/mondai/prob60/fortune_telling_9)
```ruby
n = gets.to_i
data_1 = {}
n.times do |i|
    name, status_1 = gets.chomp.split(" ")
    data_1[name] = status_1
end

data_2 = {}
n_2 = gets.to_i
n_2.times do |i|
    status_1 , status_2 = gets.chomp.split(" ")
    data_2[status_1] = status_2
end

kumiawase = []
j = 0
data_1.each do |i|
    kumiawase << data_2.select {|x,y| x == i[1]}.values.join
    puts "#{i[0]} #{kumiawase[j]}"
    j += 1
end
```

### [C010:安息の地を求めて]

```ruby
a,b,r = gets.split(" ").map(&:to_i)
n = gets.to_i
trees =[]
n.times do |i|
    x,y = gets.split(" ").map(&:to_i)
    if (x-a)**2 + (y-b)**2 >= r**2
        puts "silent"
    else
        puts "noisy"
    end
end
```