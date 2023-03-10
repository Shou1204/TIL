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