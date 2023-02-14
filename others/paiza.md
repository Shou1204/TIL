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