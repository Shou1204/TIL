# 学習の覚書
主にpaizaで練習問題をこなしての学習メモです。
---
## 値入力の基本
- 文字列
```ruby
gets.chomp
```
- 数字
```ruby
gets.to_i
```

### 入力数が多い時は配列に値を追加する
- 例.1000個の値を入力し、1000個の値を出力
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

# rubyでの用途別メソッド
## 文字列から削除
- 変数以外の文字か判定して、含まれていない文字列を`<<`でresultに追加している。
```ruby
vowels = "aiueoAIUEO"
    result = ""
    s.each_char do |char|
        result << char unless vowels.include?(char)
    end
```

## 配列を使う
- 長さ n の配列を生成することができる
```ruby
Array.new(n)
```

- １０回入力して10回putsするプログラム。
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

## 分割する
### splitメソッド
- 改行（改行は`\n`でもできる。「optキー」＋「¥」でバックスラッシュ「\」をうてる。）

`文字列.split(区切り文字)`
```ruby
s, t = 'Hello paiza'.split(' ')
puts s
puts t
# 出力例 
Hello
paiza
```
