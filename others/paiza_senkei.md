# paiza線型探索
- [paiza線型探索](#paiza線型探索)
  - [【指定された値の探索】指定された値の位置 3](#指定された値の探索指定された値の位置-3)
  - [点と点の距離](#点と点の距離)
  - [長方形に含まれる点 Ruby編](#長方形に含まれる点-ruby編)
  - [成績優秀者の列挙](#成績優秀者の列挙)
  - [【特殊な探索】 成績優秀者の列挙 ](#特殊な探索-成績優秀者の列挙-)
  - [第 k 要素の探索】k番目に大きな値 ](#第-k-要素の探索k番目に大きな値-)





## [【指定された値の探索】指定された値の位置 3](https://paiza.jp/works/mondai/sequence_search_problems/ruby/sequence_search_problems_search_value_boss/result?token=4373caf49057f9867a0ec4af6d7cc12f)

```ruby
n = gets.to_i
s = gets.split(" ").map(&:to_i)
k = gets.to_i

count = 0
s.each do |i|
    count += 1
    if i == k
        puts count
    end
end
```

## [点と点の距離](https://paiza.jp/works/mondai/sequence_search_problems/sequence_search_problems_search_condition_step4)

- 点nを含む条件を忘れないように（重要）

```ruby
n = gets.to_i
s = []
(0...n).each { |i| s << gets.split(" ").map(&:to_i)}
k = gets.to_i

target_x , target_y = s[-1]

count = 0

s.each do |x,y|
    m = (x- target_x).abs + (y - target_y).abs
    if m <= k
        count += 1
    end
end
puts count
```

## [長方形に含まれる点 Ruby編](https://paiza.jp/works/mondai/sequence_search_problems/sequence_search_problems_search_condition_step5)

```ruby
n = gets.to_i
s = []
(0...n).each { |i| s << gets.split(" ").map(&:to_i)}
xs = gets.split(" ").map(&:to_i)
ys = gets.split(" ").map(&:to_i)

x_max = xs.max
x_min = xs.min
y_max = ys.max
y_min = ys.min

count = 0

s.each do |x,y|
    
    if x <= x_max && x >= x_min && y <= y_max && y >= y_min
        count += 1
    end
end
puts count
```

## [成績優秀者の列挙](https://paiza.jp/works/mondai/sequence_search_problems/sequence_search_problems_search_condition_step6)

```ruby
n = gets.to_i
student = []
(0...n).each { |i| student << gets.split(" ")}
border = gets.to_i

success = []

student.each do |x,y|
    if y.to_i >= border
        success << x
    end
end
puts success
```

## [【特殊な探索】 成績優秀者の列挙 ](https://paiza.jp/works/mondai/sequence_search_problems/sequence_search_problems_search_condition_boss)

```ruby
n = gets.to_i
student = []
(0...n).each { |i| student << gets.split(" ")}
lower, upper = gets.split(" ").map(&:to_i)

success = []

student.each do |x,y|
    if lower <= y.to_i &&  y.to_i <= upper
        success << x
    end
end
puts success
```

## [第 k 要素の探索】k番目に大きな値 ](https://paiza.jp/works/mondai/sequence_search_problems/sequence_search_problems_kthmax_boss)

```ruby
n = gets.to_i
s = gets.split(" ").map(&:to_i)
s = s.sort
k = gets.to_i
puts s[-k]
```