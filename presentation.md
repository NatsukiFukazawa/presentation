---
theme: "black"
transition: "slide"
slideNumber: true
title: "プリンシプルになろう"

---

## プリンシプルになろう

<span style="font-size:20px;">上田勲. プリンシプル オブ プログラミング 3年目までに身につけたい 一生役立つ101の原理原則</span>

---

### 本発表の目的

- この本から得られるプログラミングにおける「視点」「見方」に関するプリンシプルに触れる

- 紹介した「視点」をもとに実際に問題を解いてみる

---

<img src="./principle.jpeg" style="border:none;box-shadow:none;">

どんな本？

---

プリンシプルとは？

プログラミングの指針となる「前提」「原則」

「思想」「習慣」「視点」「手法」「法則」のこと

---

どのような人向けか？

プログラミング言語の文法を覚えて、コードは書けるようになったけれど、いまひとつ「よいコード」にならない…{.fragment}

---

こんなことありませんか？

<span style="font-size:30px;">書いたコードを修正すると、予想外のところに影響が出る</span>{.fragment}

<span style="font-size:30px;">書いたコードに機能を追加しようとしても、いったいどこを修正すればよいのかわからない</span>{.fragment}

<span style="font-size:30px;">書いたコードに機能を追加しようとしても、まったくその余地がない</span>{.fragment}

<span style="font-size:30px;">書いたコードに仕様変更が入ると、その部分がすべて書き直しとなる</span>{.fragment}

---

成長の「王道」を知ることによって、技術の習得が早く、深くなる。

---

※抽象度が高い普遍的なtipsが多い{.fragment}

→読んだ中で実際に今までに感じたことと絡めた内容いくつかピックアップ{.fragment}

---

???
<div>
<img src="./readableCode.jpg" style="border:none;box-shadow:none;opacity:0.06">
</div>

---

### 1. コードを書く際に最も優先するべきことは？

--

拡張性、再利用性？

--

影響範囲を閉じ込める？

--

NO

---

「読みやすさ」が最も重要

---

#### 命名は最重要課題

---

なぜか？

<span style="font-size:25px;">書く時間　＜　読む時間</span>{.fragment}
<span style="font-size:25px;">コードを通じて、プログラマ同士がコミュニケーションするための最大の場</span>{.fragment}

<span style="font-size:25px;">名前には最大限の配慮がなされるべき</span>{.fragment}

<span style="font-size:25px;">コードを読む人へのUI</span>{.fragment}

---

- 名前は、発音可能なものにする

- 名前は、検索可能なものにする

- 名前は、「効果」と「目的」を説明する

- 名前には、より多くの情報を詰め込むようにする。

---

例

『音声を使ってソフトウェアを操作する機能』

を命名してみよう

--

HINT: ループバックチェック

内容の説明文から名前を考えたら、その名前から内容を推測できるか確認する

--

音声認識機能{.fragment}

×{.fragment}

音声を認識して、それで「操作する」という部分が伝わらない。よって、「音声でデータを入力する機能」と受け取られかねない。{.fragment}

--

音声操作機能{.fragment}

×{.fragment}

「音声」と「操作」の関係が伝わらない。よって、「音声によって操作する機能」ではなく、「音声を操作する機能」と受け取られかねない{.fragment}

--

音声コントロール機能{.fragment}

△{.fragment}

コントロールという単語には「コピーコントロール」のような使い方もある。よって、「音声によって操作する機能」ではなく、「音声を制限する機能」と受け取られかねない{.fragment}

--

音声命令機能{.fragment}

○{.fragment}

「音声を操作する」「音声に対して操作をする」という誤解がほぼなくなる。ただし、この名前でも、「命令」が、「入力音声」ではなく、「出力音声」にかかる、と解釈されてしまう可能性はあります。{.fragment}

---

### 2. ポリシーと実装は混ぜない

ポリシーモジュール...{.fragment}

そのソフトウェアの前提に依存する、ビジネスロジックや、その他のモジュールに対する引数の選択を行う部分

実装モジュール...そのソフトウェアの前提に依存しない、独立したロジック部分

実装モジュールは再利用可能にする

ポリシーモジュールは特定の場合にあわせる

ポリシーモジュールは実装モジュールの集合

---

```javascript
function Policy(val1,val2,val3){//ポリシーモジュール
  
  implimentModule1(val1,val2)//実装モジュール
  
  implimentModule2(val3)//実装モジュール
}
```

---

### 3. 対象原理(7つの設計原理〜コード妥当性レビュー観点〜)

「形の対称性にこだわる」という原理

読む時に予測がつく{.fragment}

考慮漏れを防ぐ{.fragment}

---

例

```javascript

const TYPE = {
  RIGHT : 0,
  LEFT  : 1,
  CENTER: 2
}

if(decideType ===  TYPE.RIGHT){
  //
}else if(decideType === TYPE.LEFT){
  //
}else{//←CENTERをの時を表しているがTYPEの定義が離れていると
      //この処理がどの場合に通るか一目ではわからない
}

```

---

### ４. データはロジックよりも御し易い

人間にとって、手続きロジックは、簡単には理解することができません。一方、データ構造は、複雑なものでも比較的簡単に理解することができる。

---

```javascript
let value

switch (type) {
  case 'boolean':{
    value = true
    break
  }
  case 'number':{
    value = 1
    break
  }
  case 'string':{
    value = "STRING"
    break
  }
  default :{
    value = null
    break
  }
  }
```

---

```javascript
const valueInitializer = {
  boolean: true,
  number: 1,
  string: "STRING",
} 

let value; 

value = valueInitializer[type]
```

---

採用するデメリットも...{.fragment}

`let value = valueInitializer[type]`{.fragment}

is どこ？{.fragment}

---

一連の処理はまとめて書く。

離れているならコメントを残す。

---

### 5.驚き最小の原則（UNIX思想⑩）

使う人に驚きが少ないようなインターフェースを設計する

<span style="font-size:20px;">馴染みがあるものは、既知のものであるという期待を高めるだけに、裏切られた時の失望が大きくなる。ほとんど同じものを作るくらいなら、まったく異なるものを作った方が、ユーザーにとっては親切となる</span>

---

## まとめ

- コードを書くときは読みやすさを最優先
  - 命名は最優先課題
  - 対象原理
- ポリシーと実装は混ぜない
- 驚き最小の原則（UNIX思想⑩）
- データはロジックよりも御し易い

---

### 練習

以下を使用

[jsonplaceholder＿10users](https://jsonplaceholder.typicode.com/users "jsonplaceholderusers")

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

---

これまでを踏まえて練習問題

- jsonplace holder 10users 全ての項目でソートをかける
  - 降順、昇順に対応
  - 住所は東京との距離
  - `"phone" "website" "company"`は除外

- 関数は命名はきちんとする　引数と返り値だけ指定

---

５分

---

### 他の内容

---

<span style="font-size:25px;">よいプログラマはよいコードを書く。偉大なプログラマはよいコードを借りてくる</span>{.fragment}

<span style="font-size:25px;">経験を積んだプログラマは、経験を積んだなりの高級なコードを書きたくなる。その誘惑に負けないようなメンタリティを持つ必要がある</span>{.fragment}

<span style="font-size:25px;">早い段階での「速いコード」は設計を破綻させる 部分に対する半端な最適化が、全体の最適化の妨げになる</span>{.fragment}

---

<span style="font-size:25px;">コードの必要条件・十分条件</span>{.fragment}

<span style="font-size:25px;">「コードを書く」コードを書く</span>{.fragment}

<span style="font-size:25px;">より良いやり方を求め続ける</span>{.fragment}

<span style="font-size:25px;">1つの仕事をするシンプルなソフトウェアが作成できたら、そこ
に新機能やオプションを付ける誘惑に負けないようにする</span>{.fragment}

<span style="font-size:25px;">プロトタイプを「できるだけ早く」作る、機能仕様書待たない</span>{.fragment}

---

<img src="./readableCode.jpg" style="border:none;box-shadow:none;">

リーダブルコードと何が違った？

---

<span style="font-size:25px;">リーダブルコードは読みやすい(理解しやすい)コードの書き方重視で実例が豊富</span>

<span style="font-size:25px;">本書はプログラマはこうあるべきであという普遍的情報をプリンシプルとして紹介
→網羅的ではあるが抽象的
</span>

---

最後に

---

プログラマに課金することが重要

ハードウェアやソフトウェアの購入を抑制するのは、経費節減のためです。しかし、設備の費用とプログラマの費用は、比較にならないほど後者が高価{.fragment}

---

おわり

---

- [ ] 課題（できたら）
- [ ] コピペの部分修正
- [ ] リーダブルコードの比較
- [ ] ポリシーと実装は混ぜないの例（まとめる）

---

| 違い |           リーダブルコード           |       本書        |
| ---- | :----------------------------------: | :---------------: |
| 実例 |              ○<br>豊富               | △<br>ほとんどなし |
| 内容 | 読みやすいコードを<br>書くためのtips |                   |

<span style="font-size:25px;"> リーダブルコードは読みやすいコードの書き方重視で実例を交えながら</span>

<span style="font-size:25px;"></span>