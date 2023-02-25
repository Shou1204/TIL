
- [paiza問題](#paiza問題)
    - [C104:虫食い算](#c104虫食い算)
    - [C048:タダ飲みコーヒー](#c048タダ飲みコーヒー)
    - [五目並べ（斜め） (paizaランク C 相当)](#五目並べ斜め-paizaランク-c-相当)
    - [C083:売上の発表](#c083売上の発表)
    - [C039:古代の数式](#c039古代の数式)
    - [C056:テストの採点](#c056テストの採点)
    - [辞書 (paizaランク C 相当)](#辞書-paizaランク-c-相当)
    - [シミュレーション (paizaランク C 相当)](#シミュレーション-paizaランク-c-相当)
    - [C060:辞書の作成 再チャレンジ採点結果](#c060辞書の作成-再チャレンジ採点結果)
    - [五目並べ（縦） Ruby編」](#五目並べ縦-ruby編)
    - [五目並べ（斜め）](#五目並べ斜め)
    - [五目並べ Ruby編](#五目並べ-ruby編)
    - [1人の占い結果 Ruby編](#1人の占い結果-ruby編)
    - [占い Ruby編](#占い-ruby編)
    - [\[C010:安息の地を求めて\]](#c010安息の地を求めて)
    - [\[C085:壊れかけのキーボード\]](#c085壊れかけのキーボード)
    - [マップの扱い 1】マップの書き換え・1 マス Ruby編](#マップの扱い-1マップの書き換え1-マス-ruby編)
    - [【マップの扱い 2】マップの書き換え・縦横 Ruby編](#マップの扱い-2マップの書き換え縦横-ruby編)
    - [マップの扱い 3】マップの判定・縦横斜め Ruby編](#マップの扱い-3マップの判定縦横斜め-ruby編)
    - [C072:モンスターの進化](#c072モンスターの進化)
    - [C093:【キャンペーン問題】下桁ルール](#c093キャンペーン問題下桁ルール)
    - [C013:嫌いな数字](#c013嫌いな数字)
    - [C097:プレゼント応募企画](#c097プレゼント応募企画)
    - [C014:ボールが入る箱](#c014ボールが入る箱)
    - [C115:渋滞の距離](#c115渋滞の距離)
    - [C099:折り紙の貼り合わせ](#c099折り紙の貼り合わせ)
    - [C088:RPGでお買い物](#c088rpgでお買い物)
    - [C116:あたり棒の検査](#c116あたり棒の検査)
    - [C035:試験の合格判定](#c035試験の合格判定)
    - [C101:【2021年Xmas問題】ラッキーデイ](#c1012021年xmas問題ラッキーデイ)
    - [C067:【ハッカー入門コラボ問題】数字の調査](#c067ハッカー入門コラボ問題数字の調査)
    - [C040:【ロジサマコラボ問題】背比べ](#c040ロジサマコラボ問題背比べ)
    - [C052:ゲームの画面](#c052ゲームの画面)
    - [C105:カードのスコア](#c105カードのスコア)
    - [【条件判定 1】郵便料金 Ruby編](#条件判定-1郵便料金-ruby編)
    - [C024:ミニ・コンピュータ](#c024ミニコンピュータ)
    - [C030:白にするか黒にするか](#c030白にするか黒にするか)
- [苦戦したもの](#苦戦したもの)
    - [C026:ウサギと人参](#c026ウサギと人参)
    - [C096:夏休み](#c096夏休み)
    - [C119:お菓子かいたずらか](#c119お菓子かいたずらか)
    - [【条件判定 3】過剰コンプライアンス Ruby編](#条件判定-3過剰コンプライアンス-ruby編)
    - [B128:簡易的二次元バーコード\]](#b128簡易的二次元バーコード)
    - [B107:カードシャッフル](#b107カードシャッフル)
- [新しい発見があった問題](#新しい発見があった問題)
    - [C037:アニメの日時](#c037アニメの日時)
    - [C074:【クロニクルコラボ問題】文章サイズ変更](#c074クロニクルコラボ問題文章サイズ変更)
    - [【全探索 1】高い寿司を食いたい！ Ruby編](#全探索-1高い寿司を食いたい-ruby編)
  - [Bランクレベルアップ問題](#bランクレベルアップ問題)
    - [【文字列 1】疑似数字 Ruby編](#文字列-1疑似数字-ruby編)
    - [【文字列 2】super long int (paizaランク C 相当)](#文字列-2super-long-int-paizaランク-c-相当)
    - [【文字列 3】p4!2@ Ruby編](#文字列-3p42-ruby編)
    - [【配列 1】平面で計算 Ruby編](#配列-1平面で計算-ruby編)
    - [計算 2】疑似乱数 (paizaランク C 相当)](#計算-2疑似乱数-paizaランク-c-相当)
    - [【シミュレーション 2】perfuct shuffle Ruby編](#シミュレーション-2perfuct-shuffle-ruby編)



# paiza問題

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

### [C014:ボールが入る箱](https://paiza.jp/works/challenges/48/page/result)

```ruby
n, r = gets.split(" ").map(&:to_i)
(1..n).each do |i|
    box_size = gets.split(" ").map(&:to_i)
    count = 0
    box_size.each do |size|
        count += 1 if r * 2 <= size
    end
    puts i if count == 3
end
```

### [C115:渋滞の距離](https://paiza.jp/works/challenges/560/page/result)

```ruby
n,m = gets.split(" ").map(&:to_i)
total = 0
(1..n).each do |i|
    wide = gets.to_i
    total += wide if m >= wide
end
puts total
```

### [C099:折り紙の貼り合わせ](https://paiza.jp/en_try/challenges/488/page/result)

```ruby
n,d = gets.split(" ").map(&:to_i)
over = 0
n.times do |i|
    over += gets.to_i
end
puts (n * d - (over)) * d
```

### [C088:RPGでお買い物](https://paiza.jp/en_try/challenges/424/page/result)
```ruby
n = gets.to_i
prices = gets.split(" ").map(&:to_i)
t , q = gets.split(" ").map(&:to_i)
q.times do |i|
    item_num , number = gets.split(" ").map(&:to_i)
    item_price = prices[item_num - 1] * number
    if item_price <= t
        t -= item_price
    end
end
puts t
```

### [C116:あたり棒の検査](https://paiza.jp/challenges/566/retry_result/e48a9390b8efd06d598acfbdea6c9681)

```ruby
n,m = gets.split(" ").map(&:to_i)
kuji = gets.chomp.split(" ")
count = 0
kuji.each do |i|
    if i == "0"
        count += 1
        return puts "NG" if count >= m
    else
        count = 0
    end
end
puts "OK"
```
### [C035:試験の合格判定](https://paiza.jp/career/challenges/153/page/result)
```ruby
# 繰り返し回数
n = gets.to_i

# 合格した人数
count = 0

# 生徒ごとに判定する
n.times do |i|
    total = 0 #合計得点
    select_score = 0 # 文系、理系のどちらかの点数

    # 最初が文字列なのでto_iはしない
    student = gets.chomp.split(" ")

    category = student.shift #先頭だけ文字列なので取り出す

    # 選択科目の合計点数を計算
    if category == "l"
        select_score = student[3].to_i + student[4].to_i
    else
        select_score = student[1].to_i + student[2].to_i
    end

    # 全科目の合計得点
    student.each do |i|
        total += i.to_i
    end

    # 全科目と選択科目の両方が基準を超えていれば合格の判定
    if select_score >= 160 && total >= 350
        count += 1 # 合格したら人数が増える
    end
end

puts count
```

### [C101:【2021年Xmas問題】ラッキーデイ](https://paiza.jp/career/challenges/498/page/result)

```ruby
# ラッキーデイを設定、検索したいので文字列で
lucky = gets.chomp.to_s

# ラッキーdayのカウント
count = 0

# 検索するので文字列にする
# 365日なので0から始めた場合は365が含まれないことに注意
("0"..."365").each do |i|
    if i.include?(lucky)
        count += 1
    end
end

# 結果を表示
puts count
```

### [C067:【ハッカー入門コラボ問題】数字の調査](https://paiza.jp/challenges/share/gmp6ZpE1LbrEUqY1_WUWd_MbOYEReQWqHrUN3c4xhhs?source=social)
- ポイントはformatメソッドで２進数に変換すること
```ruby
# 調べたいケタの数nと調べたい数字を取得
n , target = gets.split(" ").map(&:to_i)

# 数字を2進数に変換
number = format("%b", target).to_s

# 添字通りの順番ではないので全体の桁数が必要
number_size = number.size

# それぞれのケタの数字を出力
n.times do |i|
    keta = gets.to_i
    puts number[number_size - (keta)]
end
```
- 文字列の長さは必要ないことに気づいた
- 文字列[-x]で末尾から-xの文字を取り出せる
- 以下が書き直したもの

```ruby
# 調べたいケタの数nと調べたい数字を取得
n , target = gets.split(" ").map(&:to_i)

# 数字を2進数に変換
number = format("%b", target).to_s

# それぞれのケタの数字を出力
n.times do |i|
    keta = gets.to_i
    puts number[ - keta]
end
```

### [C040:【ロジサマコラボ問題】背比べ](https://paiza.jp/en_try/challenges/181/page/result)

- ポイント 最大値、最小値を変数で作成すること
```ruby
n = gets.to_i

# 最大と最小の範囲の変数を作成
max = 201.0 # これより小さかったら入れ替えるのでわざと大きい範囲外の値
min = 0.0

# 比較の数だけ最小値、最大値を比較し、入れ替えていく
n.times do |i|
    up_down , size = gets.chomp.split(" ")
    size = size.to_f

    if up_down == "le"
        max = size if max > size
    else
        min = size if min < size
    end
end

puts "#{min} #{max}"
```

### [C052:ゲームの画面](https://paiza.jp/en_try/challenges/246/page/result)
- ポイント、-の値が入力されることもありうるので絶対値にすること
```ruby
h, w = gets.split(" ").map(&:to_i)
dy, dx = gets.split(" ").map(&:to_i)
puts (h * dx).abs + (w * dy).abs - (dx * dy).abs
```

### [C105:カードのスコア](https://paiza.jp/works/challenges/517/page/result)

```ruby
n = gets.to_i

# 数字を取得するが、昇順にソートすること
num = gets.split(" ").map(&:to_i).sort

# 合計値
total = 0

# 配列のインデックスを表現
count = 0


num.each do |i|
    # 次の数字が今の数字より1大きいかどうかを判定（先にソートが絶対に必要！）
    # 連番でなければ、今の数字でブロックが終了するので今の数字を合計値に足す
    if i + 1 != num[count + 1]
        total += i
    end
    # インデックが１増える
    count += 1
end

# 合計値を表示
puts total
```

### [【条件判定 1】郵便料金 Ruby編](https://paiza.jp/works/mondai/b_rank_new_level_up_problems/b_rank_new_level_up_problems__posting_fee/edit?language_uid=ruby&t=e57a181a2a94525d47b3b0dbccbb20d2)

- 基本的には条件文通りの分岐で良い
- ポイントは`[a,b,c].max`の記述で[]内の最大値を取り出すところか
```ruby
y,x,h = gets.split(" ").map(&:to_i)
l1,l2,l3,l4,l5 = gets.split(" ").map(&:to_i)
m1,m2,m3,m4,m5,m6 = gets.split(" ").map(&:to_i)
if h <= l1
    if [y,x].max <= l2
        puts m1
    elsif x + y <= l3
        puts m2
    else
        puts m3
    end
else
    if [x,y,h].max <= l4
        puts m4
    elsif (x+y) <= l5
        puts m5
    else
        puts (x * y * h) * m6
    end
end
```

### [C024:ミニ・コンピュータ](https://paiza.jp/works/challenges/91/page/result)

```ruby
n = gets.to_i
# 変数1、変数2を初期化しておく
int_1 = 0
int_2 = 0

n.times do |i|
    # 文字列と数字が混じっているので,変換はしない
    str = gets.chomp.split(" ")

    # わかりやすいので頭の命令だけ分ける
    action = str.shift

    # SETの場合
    if action == "SET"
       if str[0] == "1" # 文字列のままなので""を忘れないように
           int_1 = str[1].to_i # 計算する必要があるので整数に
        else
            int_2 = str[1].to_i
        end
    # ADDの場合
    elsif action == "ADD"
        int_2 = (int_1 + str[0].to_i)
    else
    # SUBの場合
        int_2 = (int_1 - str[0].to_i)
    end
end
puts "#{int_1} #{int_2}" # それぞれの変数を出力
```
### [C030:白にするか黒にするか](https://paiza.jp/en_try/challenges/121/page/result)

```ruby
h,w = gets.split(" ").map(&:to_i)

h.times do |i|
    # 一行分読み込む
    int = gets.split(" ").map(&:to_i)

    # 読んだ配列の何文字目かを表す変数
    k = 0
    int.each do |j|
        # 128以上かどうか
        if j >= 128
            # intのk列目を変える
            int[k] = 1
         else
             int[k] = 0
        end
        k += 1 # 処理が終わったら次の列に
    end 
    # 出力、列数が変わるので式代入は使わない
    puts int.join(" ")
end
```
### [C028:単語テストの採点](https://paiza.jp/works/challenges/116/page/result)
```ruby
n = gets.to_i

# 合計ポイント
total = 0
n.times do |i|
    true_str, false_str = gets.chomp.split(" ")
     
     # まず、長さが合っているかどうか
     # 会っていなれば0点確定のため
     if true_str.size == false_str.size

        # 何文字合っているかのカウンター
        count = 0
        
        # 一文字ずつ合っているか確認して合ってればカウンターをたす
        true_str.size.times do |j|
            count += 1 if true_str[j] == false_str[j]
        end
        
        # カウンターが文字数なら完全一致ということ
        # 完全一致の場合
        if count == true_str.size
            total += 2
        # 一文字違いの場合
        elsif count == true_str.size - 1
            total += 1
        end
        
    end
end
# ポイントを出力
puts total
```







# 苦戦したもの
### [C026:ウサギと人参](https://paiza.jp/challenges/104/retry_result/fc2a11b179815c59e673ceb4bb4a9636)
```
Rabbit社の社長はウサギが大好きで、 社内で1匹のウサギを飼育することにしました。
ウサギが人参を好むことは広く知られています。 また、ウサギに詳しい社員によると、 人参は糖分が多いため与えすぎるのは良くないようです。

そこで、人参は1日1本だけ与えることにし、 特に糖分が許容範囲内で質量が大きい人参を選ぶことにしました。

プログラマーであるあなたはRabbit社の依頼を受け、 1 から N で番号付けられた N 個の人参のデータを入力として、 糖分が許容範囲内で質量の最も大きい人参を見つけるプログラムを作成することになりました。

糖分には基準値Sと許容誤差 p があり、 糖分が S - p 以上 S + p 以下ならば許容範囲内となります。
また、糖分が許容範囲内で質量の最も大きい人参 が複数ある場合は、それらのうち番号の最も小さいものを知ることができれば十分です。
```
```ruby
n, s, p = gets.split.map(&:to_i)

# 質量が最大のものをキーブしておくための変数
# 最大値を更新した時に中身を変える
w_max = 0

# 質量が最大のものの番号を記録しておくための変数
ninjin_number = 0

# 糖度の条件を満たして、かつ質量が最大を超えるものを選別
n.times do |i|
  w, sugar = gets.split.map(&:to_i)
    if (s-p) <= sugar && sugar <= (s + p)
        if w > w_max # キープしている最大質量より上なら入れ替える
            w_max = w
            ninjin_number = i + 1 # 番号は1~なので
        end
    end
end

# 糖度の条件を満たすものがあったなら番号を表示する
# 条件を満たしているならw_maxは更新されているはず
if w_max != 0
    puts ninjin_number
else
    puts "not found"
end
```

### [C096:夏休み](https://paiza.jp/en_try/challenges/475/retry)
```
子供は夏休みまっただ中。家族や親戚を誘ってお出かけしたいですが、みんなで休みを合わせないといけません。
子供を除いたお出かけに行くメンバーの数と、各メンバーの休みを取れる期間が与えられます。その中でメンバー全員に共通する日があれば "OK"、なければ "NG" と出力してください。
```
- 間違いのあるコード
- テストコードの一部を満たさない
- どこが悪いのだろうか？
```ruby
n = gets.to_i
day_start, day_last = gets.split(" ").map(&:to_i)
days =[]
(n-1).times { |i| days << gets.split(" ").map(&:to_i)}

# 考え方として最初のメンバーの日付に含まれているかどうかを判定する
# 含まれるには他のメンバーの初日か終日のどちらか一つでも含まれていれば良い
days.each do |day|
count = 0
    (day_start..day_last).each do |j|
        if day[0] == j || day[1] == j
            count += 1
        end
    end
    return puts "NG" if count == 0
end
puts "OK"
```

- 以下は書き換えたもの
- 方針を変えて積集合で値を取得した
```ruby
n = gets.to_i
day_start, day_last = gets.split(" ").map(&:to_i)

# 共通の休暇期間に含まれる日付の範囲
common_days = (day_start..day_last).to_a

(n-1).times do |i|
  # 各メンバーが休暇を取る日付の範囲
  member_start, member_last = gets.split(" ").map(&:to_i)
  member_days = (member_start..member_last).to_a

  # 積集合で共通の日を取り出す
  common_days &= member_days
end

# 共通の日が空かどうか
if common_days.empty?
  puts "NG"
else
  puts "OK"
end
```

### [C119:お菓子かいたずらか](https://paiza.jp/en_try/challenges/583/page/result)
```
今日はハロウィン。Paiza 町に住む女の子 Alice は、お菓子を貰いに近所の家を巡ろうと考えました。
Paiza 町には N 軒の家があり、それぞれ 1 から N で番号付けられています。
Alice は 1 番の家から順にインターホンを押して回り、すべての家を回り終えると自宅に帰ります。

一方で、Paiza 町に住む M 人の男の子たちが、お菓子をもらえなかった腹いせに、それぞれ N 軒の家のどこかに隠れて、お菓子を貰いに来た子供を驚かせているようです。
Alice は怖がりな子であるため、驚かされてしまったらお菓子を貰わずに次の家を目指し一目散に走りだします。
しかし、次の家でもまた驚かされてしまうかもしれません。
Alice は K 軒の家で連続して驚かされると、泣き出して自宅に帰ってしまいます。

M 人の男の子たちが隠れている家がわかるとき、Alice が貰えるお菓子の個数を計算するプログラムを作成してください。
```

```ruby
n,m,k = gets.split(" ").map(&:to_i)

# 男の子がいる家の番号の配列
boys =[]
m.times {|i| boys << gets.to_i}

# 2回連続で男の子のいる家にあたるかどうかのカウンター
count_2 = 0

# あめの数
total = 0

# 家の番号の数を繰り返す
(1..n).each do |home|

    count = 0 # その家に男の子がいるかどうかのカウンター

    boys.each do |boy|
        # 男の子がいなければカウンターを一つ足す
        if boy != home
            count += 1
        end
    end

    # 男の子がその家にいたかどうか
    if count == m # 居なかった場合
        total += 1 
        count_2 = 0 # 連続カウンターリセット
    else
        count_2 += 1 # 居た場合は連続カウンターをたす

        # k回でリセットなのでその時までのあめの数を出力
        return puts total if count_2 == k 
    end
end
# リセットされなかった場合のあめの数を出力
puts total
```
- 連続で男の子がいた場合をどう定義するかで迷って、時間がかかる
- カウンターを使うのが一番考えやすいか？

改良版
- include?を使えばもっと簡単だった
```ruby
n,m,k = gets.split(" ").map(&:to_i)
boys =[]
m.times {|i| boys << gets.to_i}
# 男の子にあたるとカウンターをたす
count = 0
# あめの数
total = 0

(1..n).each do |home|

    # 今の家に男の子がいるかどうか判定
    if boys.include?(home)
        # いれば連続カウンターを足す
        count += 1
        # 連続k回ならそこでストップしてあめの数を出力
        return puts total if count == k
    else
        # いなければあめを足して、連続カウンターリセット
        total += 1 
        count = 0
    end

end
puts total
```
### [【条件判定 3】過剰コンプライアンス Ruby編](https://paiza.jp/works/mondai/b_rank_new_level_up_problems/b_rank_new_level_up_problems__over_conpriance)

```ruby
# 半分前半の文字列、後半の文字列、半分の長さを出力するメソッド
def half_length(word) # 仮引数は文字列
    word_length = word.size

    # 奇数と偶数で分ける
    # 奇数の場合は真ん中の文字が重複するため
    if word_length % 2 == 0
        half_len = (word_length / 2)
    else
        half_len = (word_length / 2) + 1 # 奇数は１文字重複する
    end
    # 3つの値を出力
    [word.slice(0,half_len), word.slice(-half_len, half_len),half_len]
end

n = gets.to_i
ng_word = gets.chomp

# 文字列前半、後半を取得
ng_word_first, ng_word_last= half_length(ng_word)

n.times do |i|
    word = gets.chomp

    # 文字列前半、後半を取得
    word_first , word_last,word_half= half_length(word)

    # 前半、後半合っているかのカウント
    count = 0

    # 前半の判定
    if word_first == ng_word_first
        word_first = "x" * word_half
        count += 1
    else
        # ngでない場合は前半をそのまま出力したいが、
        # 奇数だと重複があるので最後の文字を削除する
        word_first.slice!(-1,1) if word.size % 2 == 1
    end

    # 後半の判定
    if word_last == ng_word_last 
        word_last = "x" * word_half
        count += 1
    else
        # ngでない場合は後半をそのまま出力したいが、
        # 奇数だと重複があるので最初の文字を削除する
        word_last.slice!(0,1) if word.size % 2 == 1
    end

    # 前半、後半両方ともNGの場合と両方OKの場合、片方だけOKの時の場合分け
    if count == 2
        puts "banned"
    elsif count == 0
        puts word
    else
        puts "#{word_first}#{word_last}"
    end
    
end
```

### [B128:簡易的二次元バーコード](https://paiza.jp/works/challenges/612/retry?tk=49d1f494a31c2edbc35ac53fdfa6469d)]
- j == 0の時の条件を見落としてBランクならずだった最悪の思い出
- かなりがむしゃら感がある。。
```ruby
n = gets.chomp.split("").map(&:to_i)
row = n.size / 3
array = Array.new(n.size).map{Array.new(9, ".")}
slice_array =[]
new_array = []
row.times do |t|
    num = n.slice!(0,3)
    slice_array = array.slice!(0,3)
    num.each_with_index do |j,index|
        k = 0
        if j >= 7
            k = 2
            slice_array[0][0 + (index ) * 3..0 + (index ) * 3+2] = ["#", "#", "#"]
            slice_array[1][0 + (index ) * 3..0 + (index ) * 3+2] = ["#", "#", "#"]
        elsif j >= 4
            slice_array[0][0 + (index ) * 3..0 + (index ) * 3+2] = ["#","#","#"]
            k = 1
        end
        
        if j%3 == 1
            slice_array[k][0 + (index ) * 3]  = "#"
        elsif j%3 == 2
            slice_array[k][0 + (index ) * 3]  = "#"
            slice_array[k][1 + (index ) * 3]  = "#"
        elsif j%3 == 0 && j != 0
            slice_array[k][0 + (index ) * 3]  = "#"
            slice_array[k][1 + (index ) * 3]  = "#"
            slice_array[k][2 + (index ) * 3]  = "#"
        end
    end
    new_array += slice_array
end
new_array.each do |i|
    puts i.join
end
```
### [B107:カードシャッフル](https://paiza.jp/works/challenges/525/page/result)
```
あなたは、N 枚のカードをシャッフルするプログラムを実装することにしました。

N 枚のカードにはそれぞれ 1 から N までの整数が 1 つ、重複なく書いてあります。これらのカードは最初、整数 i (1 ≦ i ≦ N) が書かれているカードは上から i 番目に並んでいます。つまり、1 が書かれたカードが一番上に、2 が書かれたカードが上から二番目に、...、N が書かれたカードが一番下になるように重ねられています。

今回は以下の方法でカードをシャッフルをします。重ねられたカードを上から M 枚ごとのセットに分けます。ただし、一番下のセットが M 枚未満の場合は M 枚未満のまま、 1 つのセットとします。上から i 番目 (1 ≦ i ≦ M) のセットが下から i 番目のセットにくるように並び替えます。すなわち、それぞれのセットに分けたあと、一番上のセットが一番下、上から二番目のセットが下から二番目、...、一番下のセットが一番上、になるように並び替えます。

この操作を 1 回のシャッフルとします。もう一度シャッフルする際は、前回のシャッフルされた状態から同じ動作を繰り返します。
K 回シャッフルしたあとのカードの順番を出力して下さい。

入力例 1 は以下のようになります。
N = 9 なので、カードは 9 枚あります。
```
- Bランク合格の記念すべき問題
```ruby
n,m,k = gets.split(" ").map(&:to_i)

# nまでの連続した数字の配列を作成
num = []
(1..n).each {|i| num << i }

# 配列を移し替えるための入れ物が必要なので作成
# timesの中でも定義してるが最後に出力したいので、、、
set_num = []

# 一回目以外は2次配列を一時配列に直す必要があるので、一回めかどうかを判断
count = 0
k.times do |i|
    # 2回目以降にset_numを初期化するため
    set_num = []

    # セットを組み直すには、1次配列にする必要がある
    num = num.flatten if count > 0

    # 1次配列をm個ずつの2次配列にする
    num.each_slice(m){|i| set_num << i}

    # m個ずつの2次配列をセットごと逆順にする
    set_num = set_num.reverse

    # set_numを初期化したいが、値を無くすわけにいかないのでコピー
    # もっといい方法はないものか？
    num = set_num

    # 1回目を過ぎたら足す
    count += 1
end
puts set_num
```

### [C122:【2022年Xmas問題】プレゼントのセール](https://paiza.jp/challenges/595/retry_result/1319ab8fff68932a7c057b4390d434d2)

- コード自体に難しいところはないが問題文を読み違えて不正解であった
- 無料枠は一回限りの適用なのでした・・・
- Bランク合格したのにこんなとこでつまづくとは

```ruby
n, x, y = gets.split(" ").map(&:to_i)
items = []
n.times { |i| items << gets.to_i }
if n / x >= 1
    items = items.sort
    items.shift(y)
end
p items.sum
```

### [B117:回る教習車](https://paiza.jp/en_try/challenges/572/page/result)

- かなり考え方に苦労した
- 
```ruby
n = gets.to_i
car_num = []
n.times { |i| car_num << gets.to_i} # n個の要素の配列を作成

count = 0 # 周回数
exit_num = 0 # 出口に到達した最後の車の番号

# 出口に出る時は週に数えないという条件なので最後より前の番号が出るまで繰り返す
until exit_num >= n - 1
    # "1"からしか出れないのでexit_numの初期値は0に
    car_num.each do |j|
        # 配列を順番に見ていって、1から順番に当てはめてexit_numに代入していく
        if j == exit_num + 1
            exit_num = j
        end
        # 周回0で全て出口に出ていく場合もあるため
        return puts count if exit_num == n
    end
    # eachが終わると一周したということなので周回数+1
    count += 1
end
puts count
```











# 新しい発見があった問題

### [C037:アニメの日時](https://paiza.jp/en_try/challenges/165/page/result)

- 解けたがコードが助長なので、シンプルにする必要がある
```ruby
days = gets.split(" ")
month , day = days[0].split("/").map(&:to_i)
m,s = days[1].split(":").map(&:to_i)
if m >= 24
    day += m / 24
    m = m % 24
end

s = s.to_s
m = m.to_s
day = day.to_s
month = month.to_s
if s.size == 1
    s = "0" + s
end
if m.size == 1
    m = "0" + m
end
if day.size == 1
    day = "0" + day
end
if month.size == 1
    month = "0" + month
end
puts "#{month}/#{day} #{m}:#{s}"
```
- 記述を整理した後
- formatメソッドを使うとシンプルに記述ができる
- また、formatメソッドを覚えると考えつくアルゴリズムが増えそうなので要学習
```ruby
# 入力を受け取る
date, time = gets.chomp.split

# 日付の各要素を抽出
month, day = date.split('/').map(&:to_i)

# 時刻の各要素を抽出
hour, minute = time.split(':').map(&:to_i)

# 時間が 24 時間以上の場合は日付を調整する
day += hour / 24
hour %= 24

# 各要素を 2 桁に揃える
month = format('%02d', month)
day = format('%02d', day)
hour = format('%02d', hour)
minute = format('%02d', minute)

# 出力する
puts "#{month}/#{day} #{hour}:#{minute}"
```



### [C074:【クロニクルコラボ問題】文章サイズ変更](https://paiza.jp/career/challenges/357/page/result)

```ruby
# 文字列の行数、一行の文字数、変更後の一行の文字数
h , m , x = gets.split(" ").map(&:to_i)

# 初期化
words =[]

# 文字を読み込む
h.times { |i| words << gets.chomp.split("")}

# 配列を文字列にする
words = words.join

# 最終的な行数を確認する
# 行数によって繰り返し回数が変わるため
if words.size % x == 0 # 文字数を一行の文字数で割ったあまりがあるという事は一行足りないので1足す
    row = words.size/x
else
    row = words.size/x +1
end

# 前に計算した行数を出力
# sliceメソッドの破壊的に使って出力したものは削除しながら表示
row.times do |i|
    print words.slice!(0,x)
    puts ""
end
```
- ポイントは行数の求め方と`slice!`を使った文字の抜き出し方
- 文字列の場合は文字を取得するときにsliceをよく使う

### [【全探索 1】高い寿司を食いたい！ Ruby編](https://paiza.jp/works/mondai/b_rank_new_level_up_problems/b_rank_new_level_up_problems__get_richer_sushi)

- ポイントは一周すると最初に戻るというところ
- その場合は`配列[添字%全体の数]`とすると配列外の番号になると最初に戻る

```ruby
n , k = gets.split(" ").map(&:to_i)

# 最大の値を取得
max = 0

# 価格を配列として取得するため
price = []
n.times {|i| price << gets.to_i}

# 2次配列にしたいので
price = price.join(",")
price = price.split(",").map(&:to_i)

# n枚の皿全てを指定することで全ての組み合わせを試す
(0..n).each do |i|
    # k枚の合計値をsumとする
    sum = 0

    # k枚の皿を合計する
    # k枚なのでkは含めず
    (0...k).each do |j|
        # 最大のポイント (i+j)でnを超えてしまった場合は配列の最初を取得
        sum += price[(i+j)%n]
    end
    # 合計が現在までの最大以上なら入れ替える
    max = [max,sum].max
end
# 全ての組み合わせを試した結果の最大値を出力
puts max
```

## Bランクレベルアップ問題

### [【文字列 1】疑似数字 Ruby編](https://paiza.jp/works/mondai/b_rank_new_level_up_problems/b_rank_new_level_up_problems__like_numbers)

```
システム開発をしている paiza 君は、与えられた文字列から自動で電話番号を取得するプログラムを作成しようと考えました。
文字列からいきなり電話番号を取得するのは難しいと考えた paiza 君は、最初の文字と最後の文字が数字(0~9)であるような文字列を「疑似数字」として取り出すコードを作成することにしました。
文字列 S が与えられるので、そこに含まれる疑似数字を全て出力してください。
数字 1 文字の場合であっても疑似数字とみなされる点に注意してください。
```
```
入力例1
81zaaz18

出力例1
8
81
81zaaz1
81zaaz18
1
1zaaz1
1zaaz18
1
18
8
```
- 正規表現を使った方が良いのかもしれないが
```ruby
s = gets.chomp

# 正規表現ではなくこの配列に含まれるかどうかで数字か判断する
numbers = ["1","2","3","4","5","6","7","8","9","0"]

# 表示する（検索する）最初の文字を表している
(0..s.length-1).each do |i|
    # 検索する最後の文字を表している
  (i..s.length-1).each do |j|
    
    # 最初の文字がnumbersに含まれている、かつ
    # 最後の文字がnumbersに含まれているときに出力する
    if numbers.include?(s[j]) && numbers.include?(s[i])
      puts s[i..j]
    end
  end
end
```

### [【文字列 2】super long int (paizaランク C 相当)](https://paiza.jp/works/mondai/b_rank_new_level_up_problems/b_rank_new_level_up_problems__super_long_int/edit?language_uid=ruby&t=ffe87705653d614c5e713e60482cad27)

```
整数型が用意されている言語では、int や long int といった型を用いて数値を保持することが多いです。
しかし、これらの型は扱える値の上限が 10^10 程度にされていることが多いです。
そこで paiza 君は新たに 32 桁の数字を受け取ることができる型 super long int を定義することにしました。
また super long int 型の値 X から int 型のハッシュ値を求める関数 hash(X) を次の通り定義しました。
hash(X) = X を 8 桁ずつに区切って得られる 4 つの 8 桁の数字の和

super long int 型の値 X が与えられるので、hash(X) の値を求めてください。
```
```
入力例1
11111111111111111111111111111111

出力例1
44444444
```
- 簡単に解けたが、意図した解き方ではない気がする
- 桁数が増えれば通用しなくなりそう
```ruby
int = gets.to_s
int_1 = int.slice!(0,8).to_i
int_2 = int.slice!(0,8).to_i
int_3 = int.slice!(0,8).to_i
int_4 = int.slice!(0,8).to_i
puts int_1 + int_2 + int_3 + int_4
```
- 模範解答
- 無駄がない、綺麗な解き方
- こういうコードを直ぐに思いつきたい
```ruby
# 文字列で読み込む。数字だと文字列操作ができないので
x = gets.chomp

# 合計値
ans = 0

# 4個の数の和なので一つずつ和を足していく
4.times do |i|
  # 8 * i 列目 から ８文字読み込んで数字に変換、合計値に足す
  ans += x[8*i, 8].to_i
end

puts ans
```

### [【文字列 3】p4!2@ Ruby編](https://paiza.jp/works/mondai/b_rank_new_level_up_problems/b_rank_new_level_up_problems__leet_paiza)

```
英単語に含まれるアルファベットの一部を形の似た数字や記号で置き換えることを Leet といいます。Leet はパスワードやユーザー名の作成の際に便利な手法の一つです。

paiza では、エゴサーチを強化するためにツイートの中に Leet 表記された paiza が含まれているかを判定するプログラムを作成することになりました。
ツイートの文章 S が与えられるので、ツイートに "paiza" が含まれる場合は "paiza", "paiza" が含まれず Leet 表記された "paiza" が含まれる場合は "leet", どちらも含まれない場合は "nothing" と出力してください。

なお、"paiza" の leet 文字列は、"paiza" について以下の置き換えを 1 回以上おこなうことで得られる文字列をさすものとします。

・a -> 4 または a -> @
・i -> 1 または i -> !
・z -> 2
```
```
入力例1
leetp@1za

出力例1
leet
```
- ポイント
- paizaという5文字それぞれを判定するため`leet_str`という"p""a""i""z""a"それぞれの順番と対応する配列を作り、`each_char`メソッドに`.with_indexメソッド`と組み合わせてそれぞれが変換文字に対応しているか確認している
  
```ruby
n = gets.chomp

# 最終的にどれも当てはまらないとnothingになるので入れておく
result = "nothing"

# この問題のポイントでそれぞれ"paiza"の順番通りに変換できる文字を入れる
# each_char.with_indexとの組み合わせを見据えている
leet_str = ["p", "4a@","i1!","z2","4a@"]

# 5文字を抜き出すので-5にしないと最後文字数が少なくなる
(0..n.size-5).each do |i|
    # leet文字と5文字ともあっているかを数えるカウンター
    count = 0
    word = n[i,5] # 5文字抜き出す

    # 文字列から１文字ずつ取り出して,0から番号を振る
    # これがleet_strと対応している
    word.each_char.with_index do |c,i|
        if leet_str[i].include?(c)
            count += 1

            # 5文字ともあっているとleet文字だと確認できる
            result = "leet" if count == 5
        end
    end
end

# paizaの文字列があるか確認する
# leetより先に書くと上書きしてしまうので最後に記述
if n.include?("paiza")
    result = "paiza"
end
# 結果を表示、どれにも当てはまらなければ初期値になる
puts result
```

### [【配列 1】平面で計算 Ruby編](https://paiza.jp/works/mondai/b_rank_new_level_up_problems/b_rank_new_level_up_problems__calculate_in_two_dimensions)

```
N × N の二次元配列 A が与えられるので、N 要素からなる縦列・横列・斜め列の和のうち、最大のものを求めてください。
```
- ポイントは斜めの合計をきちんと取得できるかどうか
```ruby
n = gets.to_i
# 最大値
max = 0
# 数字の二次元配列を定義
int =[]

# 配列を取得しながら、横だけは計算
n.times do |i|
    yoko = gets.split(" ").map(&:to_i)
    int << yoko
    # 横の合計値が今の最大値より上なら最大値にする
    max = yoko.sum if max < yoko.sum
end

# 縦の計算
n.times do |i| # iは縦
    total = 0 # 縦の合計値
    n.times do |j|
        total += int[j][i] # jは横
    end
    max = total if max < total
end

# 最大値の計算はメソッド外なので外で定義
r_down = 0
l_down = 0
n.times do |i|
    # 左上から右下
    r_down += int[i][i]
    # 右上から左下
    l_down += int[i][n-1-i] # 範囲外を参照しないように注意
end
# 両斜めの大きい方が最大値より多いかどうか、大きければ入れ替え
max = [r_down,l_down].max if max < [r_down,l_down].max

puts max
```

### [計算 2】疑似乱数 (paizaランク C 相当)](https://paiza.jp/works/mondai/b_rank_new_level_up_problems/b_rank_new_level_up_problems__similar_randamize)

```
指定した範囲内の値を一様ランダムに出力する装置を乱数生成機といい、出力された数値を乱数といいます。
この乱数は乱択アルゴリズムなどで利用されており、IT の分野で大きな役割を果たしています。
この乱数を手元で再現する方法として疑似乱数というものがあります。
この疑似乱数は、乱数を得る代わりに事前に用意しておいた計算式の結果を乱数として採用するというものです。

この問題では試しに以下のような計算式によって定められた疑似乱数生成機を用いて、乱数を N 個(rnd_1, ..., rnd_N)生成してみましょう。

rnd_i = (X^i + X^{i-1} ... + X^1) mod M
```
```
入力例1
2 1000 5

出力例1
2
6
14
30
62
```
- ポイントは%mは最終的に計算すること
```ruby
x,m,n = gets.split(" ").map(&:to_i)
total = 0
(1..n).each do |i|
    total +=  (x**i)
    puts total % m
end
```

### [【シミュレーション 2】perfuct shuffle Ruby編](https://paiza.jp/works/mondai/b_rank_new_level_up_problems/b_rank_new_level_up_problems__perfect_shuffle)

```ruby
n = gets.to_i
cards = []
("S_1".."S_13").each {|i| cards << i}
("H_1".."H_13").each {|i| cards << i}
("D_1".."D_13").each {|i| cards << i}
("C_1".."C_13").each {|i| cards << i}
n.times do |i|
    up = cards.shift(26)
    down = cards    
    cards = []
    (0..25).each do|j|
        cards << up[j]
        cards << down[j]
    end
end
puts cards
```
