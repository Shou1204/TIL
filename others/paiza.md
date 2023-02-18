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

### [C085:壊れかけのキーボード]
```ruby
numbers = gets.split(" ").map(&:to_i)
hash = {}
j= 0

# { "a" => 1, "b" => 2 ...}のようなハッシュを作成
("a".."z").each do |i|
    hash[i] = numbers[j]
    j += 1
end

words = gets.chomp.split("")

result = []
words.each do |w|
    hash.each do |h|
        # 使用回数の残っているもののみをresultの配列に入れていく
         if w == h[0] && result.count(w) < h[1]
            result << w
        end
    end
end
print result.join
```

### [マップの扱い 1】マップの書き換え・1 マス Ruby編](https://paiza.jp/works/mondai/b_rank_new_level_up_problems/b_rank_new_level_up_problems__get_one)

```ruby
# 行数と列数を取得
h,w = gets.split(" ").map(&:to_i)

# 地図の配列を作成
areas = []

# 配列に地図情報を入れる
h.times do |i|
    areas << gets.chomp.split("")
end

# 地図情報の変更の行番号、列番号を取得
x,y = gets.split(" ").map(&:to_i)

# 変更箇所を配列の中で変更する
if areas[x][y] == "."
    areas[x][y] = "#"
else
    areas[x][y] = "."
end

# 配列の中の地図情報を表示
areas.each do |line|
    line.each do |area|
        print area
    end
    puts "" # 改行が必要
end
```

### [【マップの扱い 2】マップの書き換え・縦横 Ruby編](https://paiza.jp/works/mondai/b_rank_new_level_up_problems/b_rank_new_level_up_problems__get_upsidedown)
```ruby
# 行数と列数を取得
h,w = gets.split(" ").map(&:to_i)

# 地図の配列を作成
areas = []

# 配列に地図情報を入れる
h.times do |i|
    areas << gets.chomp.split("")
end

# 地図情報の変更の行番号、列番号を取得
y,x = gets.split(" ").map(&:to_i)

# 変更箇所を配列の中で変更する
# 横の変更の配列を作る ただし範囲がだとエラーになるので範囲を絞る
areas_y =[]
areas_y << y - 1 if y -1 >= 0
areas_y << y
areas_y << y + 1 if y + 1 < h # 範囲外参照をするとエラーが出るので制限
areas_y.each do |i|
    if areas[i][x] == "."
        areas[i][x] = "#"
    elsif areas[i][x] == "#"
        areas[i][x] = "."
    end
end
# 縦の変更
# (n,n)の組み合わせが重複するので "x+0"は配列に入れない
areas_x =[]
areas_x << x - 1 if x -1 >= 0
areas_x << x + 1 if x + 1 < w # 範囲外参照をするとエラーが出るので制限
areas_x.each do |i|
    if areas[y][i] == "."
        areas[y][i] = "#"
    elsif areas[y][i] == "#"
        areas[y][i] = "."
    end
end

# 配列の中の地図情報を表示
areas.each do |line|
    line.each do |area|
        print area
    end
    puts "" # 改行が必要
end
```
- マップの j 行 i 列のマスに隣接している要素は、それぞれ S[i][j-1], S[i][j+1], S[i-1][j], S[i+1][j] で受け取れる。


- 範囲外参照でエラーが出るので注意


### [マップの扱い 3】マップの判定・縦横斜め Ruby編](https://paiza.jp/works/mondai/b_rank_new_level_up_problems/b_rank_new_level_up_problems__get_row_col)
```ruby
# 行数と列数を取得
h,w = gets.split(" ").map(&:to_i)

# 地図の配列を作成
areas = []

# 配列に地図情報を入れる
h.times do |i|
    areas << gets.chomp.split("")
end

# 地図情報の変更の行番号、列番号を取得
target_y,target_x = gets.split(" ").map(&:to_i)

# 縦を変える 範囲はhなのでeachの中は(...)でhを除外している
(0...h).each do |y|
    areas[y][target_x] = areas[y][target_x] == "." ? "#" : "."
end

# 横を変える 範囲はhなのでeachの中は(...)でhを除外している
(0...w).each do |x|
    areas[target_y][x] = areas[target_y][x] == "." ? "#" : "."
end

# 斜めを変える
# 斜めは4通りある x,yがそれぞれ左上から(+,-),(+,+),(-,+),(-,-)
# まず範囲を絞る
(0...[h, w].max).each do |i|
    # 中心より上に変更余地があるか
    if target_y + i < h
        # 中心より右側に変更余地があるか
        if target_x+i < w
            areas[target_y+i][target_x+i] = (areas[target_y + i][target_x + i] == '.') ? '#' : '.'
        end
        # 中心より左側に変更余地があるか
        if target_x-i >= 0
            areas[target_y+i][target_x-i] = (areas[target_y + i][target_x -i ] == '.') ? '#' : '.'
        end
    end
    
    # 中心よ下に変更余地があるか
    if target_y - i >= 0
        if target_x + i < w
        areas[target_y-i][target_x+i] = (areas[target_y - i][target_x + i] == '.') ? '#' : '.'
        end
        if target_x - i >= 0
        areas[target_y - i][target_x - i] = (areas[target_y - i][target_x - i] == '.') ? '#' : '.'
        end
    end
end

# target中心は縦と横で2回変えて戻っているのでもう一回変更する
areas[target_y][target_x] = areas[target_y][target_x] == "." ? "#" : "."

# 配列の中の地図情報を表示
areas.each do |line|
    line.each do |area|
        print area
    end
    puts "" # 改行が必要
end
```
- 今回はif文を条件演算子を使ってコードを短くしている

### [C072:モンスターの進化](https://paiza.jp/works/challenges/346/page/result)
```ruby
# 値を3つ受け取って、それぞれを固有の変数にする
atk,defence,agi = gets.split(" ").map(&:to_i)

# 繰り返し回数を受け取る
n = gets.to_i

# 最終的に当てはまるジョブを入れていく配列作成
job_list =[]

# それぞれのジョブごとに判定していく
n.times do |i|
    status = gets.split(" ")

    # 配列の先頭だけジョブ名なので取り出しておく
    # 取り出さなくても構わない
    job = status.shift

    # 条件3つを満たしているかどうか判定している
    count = 0
   count += 1 if ((status[0].to_i..status[1].to_i)).include?(atk)
   count += 1 if ((status[2].to_i..status[3].to_i)).include?(defence)
   count += 1 if ((status[4].to_i..status[5].to_i)).include?(agi)
   job_list << job if count == 3
end
# ジョブが当てはまらない時だけメッセージが別なので配列の長さで判定している
if job_list.size == 0
  puts "no evolution"
else
    puts job_list
end
```
- `include?`メソッドがポイント

### [C093:【キャンペーン問題】下桁ルール](https://paiza.jp/challenges/452/retry_result/1cbbe969b7b0cd735aa0cdaf89421b8c)

```ruby
def point(score)
    ten = score == 100 ? 1 : score / 10
    one = score % 10
    total = ten + one
    result = total % 10
end

bob_score,alice_score = gets.split(" ").map(&:to_i)

if point(bob_score) > point(alice_score)
    puts "Bob"
elsif point(bob_score) < point(alice_score)
    puts "Alice"
else
    puts "Draw"
end
```
- 10の位と1の位の取得の仕方がポイント
- 100の場合だけ"割る10"が当てはまらないので分岐にしている

### [C013:嫌いな数字](https://paiza.jp/challenges/46/retry_result/e2a8ac79d4bb6dbac67331a1c5b2378c)

```ruby
# 嫌いな数字を取得、文字列で検索するので数字にはしない
target = gets.chomp

# 部屋の数（繰り返し回数）を取得
n = gets.to_i

# 部屋を取得するための配列を用意して中に入れる
rooms = []
n.times do
    rooms << gets.chomp
end

# 部屋の中からお気に入りの部屋を分別する
favorite_rooms =[]
rooms.each do |room|
    # 嫌いな数字に当てはまらなかったらお気に入りに追加
    unless room.include?(target)
        favorite_rooms << room
    end
end

# お気に入りがあるかどうかを判定してから表示
if favorite_rooms.size == 0
    puts "none"
else
    puts favorite_rooms
end
```

### [C097:プレゼント応募企画](https://paiza.jp/works/challenges/480/page/result)
```ruby
n , a ,b = gets.split(" ").map(&:to_i)
(1..n).each do |i|
    if i % a == 0 && i % b == 0
        puts "AB"
    elsif i % a == 0
        puts "A"
    elsif i % b == 0
        puts "B"
    else
        puts "N"
    end
end
```