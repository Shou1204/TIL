# paiza線型探索


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