## 基本メモ

## HTML の導入

### HTML の雛形を作る

- vscode で以下を入力

```html
html:5
```

以下が出力される

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body></body>
</html>
```

## HTML で javascript を読み込む

### script タグを使う

```html
<script>
  alert("good morning");
</script>
```

### source属性 で読み込む

```html
<script src="main.js">
  alert("good morning");
</script>
```

- `src`で読み込むと中のスクリプトは実行されない
