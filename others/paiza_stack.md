# stack問題関連まとめ

- [stack問題関連まとめ](#stack問題関連まとめ)
  - [スタック実装編 step 1](#スタック実装編-step-1)



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