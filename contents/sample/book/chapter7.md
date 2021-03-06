# クイズセクションの作り方
このチャプターではチャレンジのクイズと同じような選択問題やプログラムコード以外の穴埋め問題の作成の仕方を説明します。

## 単一選択問題を作成する
右の設問に答えなさい。

---
単一選択問題を作成するには`mcq`というセクションに正解が一つだけ定義されたクイズを定義します。
クイズの定義方法はhow-to-make-quiz.mdを参照してください。


### mcq
`1 + 1`は？

- [ ] 0
- [ ] 1
- [x] 2
- [ ] 3

## 複数選択問題を作成する
右の設問に答えなさい。

---
複数選択問題を作成するには`mcq`というセクションに正解が複数定義されたクイズを定義します。
クイズの定義方法はhow-to-make-quiz.mdを参照してください。


### mcq
次のうちプログラミング言語は？

- [x] PHP
- [ ] Git
- [x] Ruby
- [ ] Docker

## マークダウン内の穴埋め問題を定義する
右の設問に答えなさい。

---
マークダウン内での穴埋め問題を作成するには`fib`というセクションに穴埋めを含むマークダウンを定義します。

### fib

1 + 1 の答えは ${2}です。
1 + 2 の答えは ${3}です。

## 穴埋め問題をドロップダウンにする
右の設問に答えなさい。

---
穴埋め問題をドロップダウンにするには、`dropdown`セクションにドロップダウンの名前とリストを定義します。
ここではマークダウンリストの1段目に名前を、2段目にリストの内容を定義します。

本文の方では`${@dropdown([名前], 正解のインデックス)}`のように定義したドロップダウンを参照します。
正解のインデックスは`0`ベースです。

### fib

1 + 1 の答えは ${@dropdown(Q1, 2)}です。
1 + 2 の答えは ${@dropdown(Q2, 3)}です。

### dropdown
- Q1
  - 0
  - 1
  - 2
  - 3
- Q2
  - 謎
  - 不明
  - 未定
  - 3

### hint
通常のテキスト形式での穴埋めとドロップダウンを混在させることや、一つのドロップダウン定義を複数の箇所から参照することも可能です。

## 本文を外部参照する
右の設問に答えなさい。

---
fibやmcqの本文はセクション定義内に直接埋め込むこともできますが、`- file: chapter7/q1.md`のように外部ファイルを参照することもできます。

### fib

- prefix: @
- file: chapter7/q1.md

### hint
ファイルを外部参照とした場合、次のようなメリットがあります。

- 見出し(`#`や`##`など)が使える
  - セクション定義内に埋め込む場合はブック自体のシンタックスと競合するため使用できません。
- fibセクションで`prefix`を定義することによって穴埋めの開始文字を変更することができる

必要に応じて使い分けてください。
