# SwiftProjectCodingRules
---
# Overview
## Swiftプロジェクトを個人開発する際のルールまとめ
### * 命名ルール:
* 変数に関しては先頭文字小文字移行の単語を大文字で表示するローワーキャメルで命名する
```
例:
    var hogeHogeList
```

* グローバル定数、クラスごとに宣言する定数に関しては大文字のスネークケースで命名する

```
例:
    public let HOGE_HOGE_LIST

    class hogehogeMdoel {
        static let HOGE_NAME = "名前"
    }
```
* クラス名、構造体名、列挙型名、プロトコル名はアッパーキャメルを用いる
```
例:
    class MsgModel {}
    protocol MsgModelDelegate: class {}
    enum Weather: String {}
    struct Author {}
```

* Optional型(nilの値がセットできないようにする)の場合、元の名前の先頭にアンダーバーをつける
```
Optional型の宣言例:
    var name: String? // Optional
    var name: String  // 非Optional
```
```
例:
    let text: String? = "hello world"
    if let _text = text {
        xxx = _text.uppercaseString
    }

    let text: String? = "hello world"
    guard let _text = text else {
        return
    }
    xxx = _text.uppercaseString
```
### * 変数、定数定義:
* 特別な理由がない限り複数の変数定義は許可しない
* 基本的に再代入しないのであれば `let` で定義する。
* 右辺の方が明確である場合、左辺に型を記載しない
* 右辺の方が曖昧である場合、左辺に方を明記する
### * 配列の初期化宣言
Apple推奨の [CollectionType Protocol Reference](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/CollectionTypes.html) の内容に合わせる
```
空配列の初期化構文
    配列内に格納する値の型を宣言する
例:
    var someInts = [Int]()
```
### * 文字列型
文字列型としてObjective-CのNSStringとStringの2種類存在する。
SwiftのStringには互換性があるためStringを利用する
文字列結合とフォーマットを実行する際は(NSStringのメソッドを使わない)
### * 文字数の取得
厳密な文字数カウントを必要をしていない場合、 `String.characters.count`を利用する
### * 空文字の判定
空文字判定は `isEmpty` を利用する
### * 整数型


# Description
個人的に開発をするための指標のルールですので、参考にしていただける場合はあくまで参考の範囲内でお願いします。
内容に関する指摘・アドバイスなどありましたら "issue" のほうにご記載願いますm(_ _)m
## <u>作成に伴う[参考先ページ](https://qiita.com/masanori-inukai/items/663e23f2390bf52fcffd)</u>
