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