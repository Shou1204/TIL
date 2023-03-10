# stack,q問題関連まとめ

- [stack,q問題関連まとめ](#stackq問題関連まとめ)
  - [スタック実装編 step 1](#スタック実装編-step-1)
  - [スタック実装編 step 2](#スタック実装編-step-2)
  - [キュー実装編 step 1 ](#キュー実装編-step-1-)
  - [キュー実装編 step 2](#キュー実装編-step-2)
  - [2 つのキュー](#2-つのキュー)
  - [最大の区間和 ](#最大の区間和-)
    - [重要：計算量が多いときにスタックかキューを使うとタイムオーバーを回避できることがある](#重要計算量が多いときにスタックかキューを使うとタイムオーバーを回避できることがある)
  - [逆ポーランド記法](#逆ポーランド記法)
  - [括弧列](#括弧列)
  - [エスカレーター](#エスカレーター)










## [スタック実装編 step 1](https://paiza.jp/works/mondai/reviews/show/fa58002cb29af58334396d17350c2af9)

```ruby
n = gets.to_i

# stackの配列を用意
stack = []
n.times do |i|

    # コマンドと値を分けて定義
    command , val = gets.split(" ").map(&:to_i)
    
    # pushならstackに値を加える
    if command == 1
        stack << val
    else
        # popならstackの最後尾の要素を削除
        stack.pop
    end
    puts stack.join(" ")
end
```

## [スタック実装編 step 2](https://paiza.jp/works/mondai/stack_queue/stack_queue__stack_step2/edit?language_uid=ruby)

```ruby
n = gets.to_i

# stackの配列を用意
stack = []
n.times do |i|

    # コマンドと値を分けて定義
    command, a = gets.chomp.split(" ")
    
    # pushならstackに値を加える
    if command == "1"
        stack << a
    else
        puts stack.pop
    end
    puts stack.join(" ")
end
```

## [キュー実装編 step 1 ](https://paiza.jp/works/mondai/stack_queue/stack_queue__queue_step1/edit?language_uid=ruby)

```
Q 個のクエリが与えられます。空の配列 A を用意したあと、 Q 個のクエリに応じて以下の 2 種類の処理をしてください。

・ PUSH X: 配列 A の末尾に X を追加
・ POP: 配列 A の先頭にある要素を削除

各クエリの処理が終わったあと、配列 A の各要素の値を半角スペース区切りで出力してください。
```
```ruby
n = gets.to_i
stack = []
n.times do |i|
    command, a = gets.chomp.split(" ")
    
    if command == "1"
        stack << a
    else
        stack.shift
    end
    puts stack.join(" ")
end
```

## [キュー実装編 step 2](https://paiza.jp/works/mondai/stack_queue/stack_queue__queue_step2/edit?language_uid=ruby&t=f5d9d5e7e3811b01b108e615f7a3e0e9)

```
Q 個のクエリが与えられます。空の配列 A を用意したあと、 Q 個のクエリに応じて以下の 2 種類の処理をしてください。

・ PUSH X: 配列 A の末尾に 文字 X を追加
・ POP: 配列 A の先頭にある要素を出力し、削除

各クエリの処理が終わったあと、配列 A の各要素の値を半角スペース区切りで出力してください。
```
```ruby
n = gets.to_i
stack = []
n.times do |i|
    command, a = gets.chomp.split(" ")
    
    if command == "1"
        stack << a
    else
        puts stack.shift
    end
    puts stack.join(" ")
end
```

## [2 つのキュー](https://paiza.jp/works/mondai/stack_queue/stack_queue__practice_step1/edit?language_uid=ruby)

```
Q 個のクエリが与えられます。 2 つのキューを用意したあと、 Q 個のクエリを順に処理してください。各クエリは、以下の 5 つのいずれかです。

・ PUSH 1 X: 1 つ目のキューに数値 X を追加
・ PUSH 2 X: 2 つ目のキューに数値 X を追加
・ POP 1: 1 つ目のキューの先頭の要素を削除し、その値を出力
・ POP 2: 2 つ目のキューの先頭の要素を削除し、その値を出力
・ SIZE: 1 つ目のキュー、 2 つ目のキューに含まれる要素数をそれぞれ出力
```

```ruby
n = gets.to_i
stack_1 = []
stack_2 = []
n.times do |i|
    command, a, b = gets.chomp.split(" ")
    
    if command == "1"
        stack_1 << b if a == "1"
        stack_2 << b if a == "2"
    elsif command == "2"
        if a == "1"
            puts stack_1.shift
        else
            puts stack_2.shift
        end
    else
        puts "#{stack_1.size} #{stack_2.size}"
    end
end
```

## [最大の区間和 ](https://paiza.jp/works/mondai/stack_queue/stack_queue__practice_step2/edit?language_uid=ruby&t=cfbf1bc22d5f99185064eab58ddaedd9)

### 重要：計算量が多いときにスタックかキューを使うとタイムオーバーを回避できることがある
- 考え方を覚えておくこと
- queの配列を使うとタイムオーバーになるので配列を使わないで解く

```N 個の要素からなる数列 A があります。 A に含まれる連続した X 個の要素の和の最大値とその区間の左端の値を出力してください。ただし、要素の和の最大となる区間が複数ある場合はそのうちもっとも先頭の値を出力してください。
たとえば、 N = 4 , A = [2, 3, 4, 1] , X = 2 とします。連続した 2 個の要素の和が最大となる区間は A の 2 番目から 3 番目まで( 3 + 4 = 7 が最大値 )なので、最大値 7 とその区間の左端の値 3 を出力します。
```
```ruby
n, x = gets.chomp.split.map(&:to_i)
num = gets.chomp.split.map(&:to_i)

# 区間の和が最大になる左端の値
# num[0]にしているのはn==xの時はeachが作動しないため初期値を設定する必要があるため
left_num = num[0] 
tmp_sum = 0 # 区間の和

# 区間の和
(0...x).each do |i|
  tmp_sum += num[i]
end
max_sum = tmp_sum # 最初の区間最大値

# チューブの左端を一つ押し出したら、右端から一つ入ってくるイメージ
(0...n-x).each do |i|
    # 左端を引く
    tmp_sum -= num[i]
    # 右端にたす
    tmp_sum += num[i+x]
    
  if tmp_sum > max_sum
    # 左端の数
    left_num = num[i+1]
    max_sum = tmp_sum
  end
end

puts "#{max_sum} #{left_num}"
```

## [逆ポーランド記法](https://paiza.jp/works/mondai/stack_queue/stack_queue__practice_step3/edit?language_uid=ruby&t=13f4728929031cff9479f37d4bbbd995)

```
逆ポーランド記法 で書かれた数式が与えられます。
この数式を計算した結果を出力してください。
この問題は少し難しいですが、スタックを用いて解いてみましょう。
```
```ruby
n = gets.chomp.to_i
a = gets.chomp.split

# stackの入れ物を作成
st = []

# 数式を１文字ずつ判定
(0...n).each do |i|
  # 記号だった場合、1つ前と2つ前の数字を取り出す
  if a[i] == "+" || a[i] == "-"
    num1 = st.pop().to_i
    num2 = st.pop().to_i
    # 1つ前と2つ前の数字を足して、格納し直す
    if a[i] == "+"
      st.push(num1 + num2)
    # 1つ前から2つ前の数字を引いて、格納し直す
    else
      st.push(num2 - num1)
    end
  # 数字だった場合、そのまま格納する
  else
    st.push(a[i].to_i)
  end
end
# stackを表示する
# 正しく作動していれば、数字は一つ
puts st
```

## [括弧列](https://paiza.jp/works/mondai/stack_queue/stack_queue__practice_step4/edit?language_uid=ruby&t=b0bb4113d73b8fcf150f9fd75ee68758)

```
N 文字の 括弧列 S が与えられます。与えられた 括弧列 が 正しい括弧列 かどうか判定してください。

ここで、 括弧列 とは以下のように定義します。

* ( または ) または空文字のみで構成される文字列

また、 正しい括弧列 とは以下のように定義します。

1. 空文字列は正しい括弧列である。
2. 文字列 s が正しい括弧列であるとき、 ( + s + ) は正しい括弧列である。
3. 文字列 s , t が正しい括弧列であるとき、 s + t は正しい括弧列である。
```

- "(" と ")" が揃った時点で配列から値が消えていく
- stackから値が消えたなら正しい組み合わせであるということ
```ruby
n = gets.to_i
s = gets.chomp

st = []

(0...n).each do |i|
  # 配列に値が入っていて、最後の値が"(" 、s[i]が")"の場合
  if st.length > 0 && st[-1] == "(" && s[i] == ")"
    # 最後の値を削除
    st.pop
  # 当てはまらなければ追加
  else
    st.push(s[i])
  end
end

# 値が配列に残っていれば括弧が足りないということ
if st.length == 0
  puts "Yes"
else
  puts "No"
end
```


## [エスカレーター](https://paiza.jp/works/mondai/stack_queue/stack_queue__practice_step5/edit?language_uid=ruby&t=4c45be6b542206412fef33d94889fa39)

```
paiza ビルにあるエスカレーターは全長 K メートルあり、 1 秒で 1 メートル進みます。
また paiza ビルに勤める社員が N 人おり、 i 番目の社員は時刻 A_i にエスカレーターに乗ります。
各社員がエスカレーターに乗った直後に、エスカレーター上にいる人数をそれぞれ答えてください。
ただしある時刻にエスカレーターに乗る社員と降りる社員がいた場合、これは同時におこなわれます。
```

- 最初に自分で作ったプログラム
- 答えは出せるがタイムアウトになるので対策が必要
```ruby
n, k= gets.split(" ").map(&:to_i)
q = Array.new(k,0)
num = gets.split(" ").map(&:to_i)
num_max = num.max

(1..num_max).each do |i|
    if num.include?(i)
        q << 1
    else
        q << 0
    end
    q.shift
    p q.sum if num.include?(i)
end
```
- 改良版
- sumを使わないで、現在のエスカレーター上の人数をカウントしている
```ruby
n, k= gets.split(" ").map(&:to_i)
time = gets.split(" ").map(&:to_i)
que = []
next_person = 0 # 次の乗客が乗る時間
person_on_escalator = 0

# 時間毎に判定、最後に乗る人の時間までとしている
last_time = time.max
(1..last_time).each do |i|

    # 現在の時間iに乗る人がいるかを判定
    if i == time[next_person]
        que << 1 # 乗客一人を乗せる
        person_on_escalator += 1 # エスカレータ上に一人乗せる
    else
        que << 0 # 乗客が乗らないことを示す
    end
    
    # エスカレータに乗れる人数を上回ったら一人降りる
    if que.size > k
        # エスカレータから下す
        # 乗ってなければ0なのでエスカレータ上の人数は変わらない
        person_on_escalator -= que.shift
    end
    
    # 現在の時間iに乗る人がいるかを判定
    if i == time[next_person]
        p person_on_escalator # エスカレータ上の人数を表示
        next_person += 1 #+1することで次に乗る人の時間になる
    end
end
```

[箱とボール](https://paiza.jp/works/mondai/stack_queue/stack_queue__practice_step6/edit?language_uid=ruby&t=0241e994369587f0372c9f92a1bd562f)
```
幅 1 の筒状の箱に数値の書かれた直径 1 のボールを入れます。各ボールは同じ数値のボールが隣合ったときに結合し、数値が 2 倍になります。それぞれ A_i と書かれた N 個のボールがあり、順番に箱の底へ入れていきます。最終的な箱の中のようすを、箱の天井から順に出力してください。
```
```ruby
n = gets.to_i
boll = gets.split(" ").map(&:to_i)
st = []

boll.each do |i|
    #最初の一回だけ無条件でstackに格納
    if st.size == 0
        st << i
    # 最初でなければ
    else
        # stackの最後の数字と一緒なら2倍にして格納
        if i == st[-1]
            # まずstackの最後を削除して
            st.pop
            # stackに2倍した値を追加
            st << i * 2

            # stackに追加した2倍の値が前の値と同じなら処理は続く
            while st[-1] == st[-2]
                # その値を保存
                num = st[-1]
                # 同じ値2を削除
                st.pop(2)
                # stackに値の2倍を格納
                st << num * 2
            end

        # 前の数字と異なればそのまま格納
        else
            st << i
        end
    end
end
# 天井のボールから出力する
puts st.reverse
```