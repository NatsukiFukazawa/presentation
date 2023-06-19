---
theme: "black"
transition: "slide"
slideNumber: true
title: "フロントエンドテスト入門"

---

## プリンシプルになろう

<span style="font-size:20px;"> フロントエンドテスト入門</span>

---

### 本発表の目的

- フロントエンドのテストの種類と目的を理解する

---

### テストの種類と使用するライブラリ

- 単体テスト
  - 関数のテスト
  - UI コンポーネントテスト

- 結合テスト
- ビジュアルリグレッションテスト

- E2Eテスト

### 単体テスト

関数が期待する動作になっていることをテストする
仕様ツール jest

例：

```javascript

function sum(a,b){
  return a + b
}


test.describe('1+2は3'){
  sum(1,2).tobe(3)
}

```

UI コンポーネントのテスト

使用ツール storybook

```javascript


```

### 結合テスト

一連の動作を行う
使用ライブラリ

例：

```javascript

```

### ビジュアルリグレッションテスト

### E2Eテスト
