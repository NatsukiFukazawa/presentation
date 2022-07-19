---
theme: "black"
transition: "slide"
slideNumber: true
title: "プリンシプルになろう"

---

## プリンシプルになろう

<span style="font-size:20px;">上田勲. プリンシプル オブ プログラミング 3年目までに身につけたい 一生役立つ101の原理原則 (Japanese Edition)</span>

---

```javascript
declear your code
```

```javascript
var div = document.createElement("div");
```

どっちが重要だと思いますか？

---

拡張性の担保

```javascript

[
  {
    val1:"hoge",
    val2:"huga",
    valueGenerator:(oldval)=>{return newval(oldval)},
  },
  {
  ......
  },
  ...
]

```

---

この本の説明

---


### 課題

- 最初の課題 
  - jsonplace holder 10users 使って



---

今回はこれを使用します。

[jsonplaceholderusers](https://jsonplaceholder.typicode.com/users "jsonplaceholderusers")


```json
 {
    "id": 1,
    "name": "Leanne Graham",
    "username": "Bret",
    "email": "Sincere@april.biz",
    "address": {
      "street": "Kulas Light",
      "suite": "Apt. 556",
      "city": "Gwenborough",
      "zipcode": "92998-3874",
      "geo": {
        "lat": "-37.3159",
        "lng": "81.1496"
      }
    },
    "phone": "1-770-736-8031 x56442",
    "website": "hildegard.org",
    "company": {
      "name": "Romaguera-Crona",
      "catchPhrase": "Multi-layered client-server neural-net",
      "bs": "harness real-time e-markets"
    }
  }

```

--

--- 
課題

- 選択したユーザーを対象に位置が近い順にソートする関数の作成を文芸的プログラミングで記述
  意識すること

  - 拡張性を持たせる
  - まずは動くものを
  
- 決まり

- 関数は引数とか返り値を指定（型と何を表すのか）
  

```(例)

```

---


- 一旦出してもう一回要件を足す

- 

---

本発表で伝えること

- まず意識することを伝えて実際に描いてもらう
  - 

- 同様に他のことを説明して同じ題材で書いてもらう
  - どっちが良いか話し合ってもらう

- 発表　オチによりよいやり方を見つけましょう結論付ける

- おまけ
  - プログラマに課金することが重要

  -

---

1. 第３のシステム

2. 移植性と開発効率性どっち優先→移植性

---

相反するもの

- 拡張性の問題と単純な問題（）

- よいプログラマはよいコードを書く。偉大なプログラマはよいコードを借りてくる\[^1]

\[^1]:注釈テキスト注釈テキスト注釈テキスト

---

まず〜〜を意識してかく

---

沈黙は金ソフトウェアは、極力表示出力を抑えるようにします。

> 上田勲. プリンシプル オブ プログラミング 3年目までに身につけたい 一生役立つ101の原理原則 (Japanese Edition) (p.257). Kindle 版.

---

- 実用的なコード例は自分で考える

---
