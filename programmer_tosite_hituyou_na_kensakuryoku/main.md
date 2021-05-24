---
theme: default
paginate: true
headingDivider: 1
footer: "Twitter: @shun_shobon"

---



# プログラマとして必要な検索力について

### SHUN / しゅん



# 自己紹介

- 名前: SHUN / しゅん
- 学年･学科: 3年電子情報工学科
- 使用言語: JavaScript / TypeScript / Haskell など
- 得意分野: Web系全般 / CI/CD / クラウド など
- Twitter: @shun_shobon
- GitHub: @shun-shobon



# アジェンダ

- プログラマとして必要なもの
- 検索の仕方
- 情報の取捨選択について
- おすすめ拡張機能



# プログラマとして必要なものとは？



# プログラマとして必要そうなもの

- 実装力
- 設計力
- デバッグ力
- コミュニケーション能力(?)
- 英語力(?)



# もちろんこれらも必要



# 本当に必要な力



# ***検索力***



# 検索力とは

- どれだけGoogle先生と仲が良いか
- 知りたいことがあったときにどれだけ早く正確にその情報を得ることができるのか



# 検索の仕方

重要なこと: **知りたいことを単語に分割する**



# 検索の仕方 - 例

例: GolangでJSONをBodyに含めてHTTPリクエストしたい

- Golangで → go
- JSONを → json
- Bodyに含めてHTTPリクエスト → http request

**結果: `go json http request`**



# 検索の仕方 - コツ

- 日本語より英語の単語を入れよう
  - `go json http request` → 約40,100,000件
  - `go言語 json httpリクエスト` → 約317,000件



# 検索の仕方 - コツ

- 件数が極端に少ない場合 → 不必要な単語を削る
  - `go json http request` → `go json http` → `go json`
  - 最悪2単語でも割と欲しい情報が出てくるかも



# 検索の仕方 - コツ

- 知りたい内容を分割して検索してみる
  - GolangでJSONをBodyに含めてHTTPリクエストしたい
    - GolangでHTTPリクエストしたい
    - GolangのHTTPリクエストでBodyを扱いたい
    - GolangでJSONを扱いたい



# 情報の取捨選択について

検索で出てきた情報が必ずしも正しいと限らない



# 情報の取捨選択について

**ランクA**: とりあえず信じていいも良い情報

- ソースコード
- 公式ドキュメント
- 公式コミュニティ
- GitHub Issue



# 情報の取捨選択について

**ランクB**: 複数のソースで照らし合わせて正しいか確認するべき

- 個人ブログ
- Qiita
- Zenn



# 情報の取捨選択について

**ランクC**: 信じないほうが良い

- プログラミングスクールの記事
- StackOverflowを機械翻訳しただけのサイト

- その他



# おすすめの拡張機能

情報の取捨選択を楽にすることができる



# おすすめの拡張機能

**uBlacklist**

![](./ublacklist.png)

# おすすめの拡張機能

特定のサイトを検索結果に出ないようにする

さっきのランクCのサイトを先回りでブロックしておくと良い



# おすすめの拡張機能

ブロックから漏れたサイトも簡単にブロックできる

![](./ublacklist_example.jpg)



# おすすめの拡張機能

僕のブロックリスト

詳細: https://gist.github.com/shun-shobon/5eb3e9e7dd502d1db297c083dd5f4fef

```
*://www.tlcannon.com/*
*://www.it-swarm.jp.net/*
*://techacademy.jp/*
*://www.sejuku.net/*
*://living-sun.com/*
*://www.it-mure.jp.net/*
*://gitmemory.com/*
*://www.javaer101.com/*
*://bleepcoder.com/*
```



# まとめ

- 検索力はプログラマにとって最も重要
- 検索の仕方を身に着けよう
- 情報の取捨選択をできるようにしよう
- 拡張機能を使いこなそう
- ***結局は慣れなので地道に頑張ろう***

