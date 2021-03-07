---
theme: default
paginate: true
headingDivider: 1
---



# NeoVim v0.5がアツい！



# 自己紹介

- 名前: SHUN/しゅん
- 学年: 高専新3年生
- 得意言語: TypeScript、JavaScript、Haskell、など
- 得意分野: Webがチョットデキル、TSの型芸、CI/CD
- Twitter: @shun_shobon
- GitHub: @shun-shobon



# 話すこと



# NeoVimの新バージョンv0.5がアツい！



# NeoVimとは？

Vimからforkされたプロジェクト

Vimは20年近く開発が続いていて、古いコードで書かれたものが多かったりパッチの受け入れに慎重になりがち

そこで、NeoVimという新しいプロジェクトが立ち上がった

リファクタリングや新機能追加を積極的に行い、モダンなCLIエディタ(？)を目指すというもの



# v0.5とは？

NeoVimの現在のStableバージョンはv0.4

v0.5は現在絶賛開発中のバージョン(2021/03/07現在まだNightly)



# v0.5で追加(予定)の新機能

- Luaのネイティブサポート
- Treesitterのネイティブサポート
- LSP Clientのネイティブサポート



# Luaのネイティブサポート

Vimの設定ファイルがLuaで書けるようになります

```vimscript
set number

inoremap <silent> jj <Esc>
```

```lua
vim.wo.number = true

vim.api.nvim_set_keymap("i", "jj", "<Esc>", { noremap = true, silent = true })
```



# VimScriptでよくね？



# VimScriptは遅い(絶望的に)

文法が曖昧すぎてJITコンパイルが不可能

↑のせいでソースコードのパース処理を毎回行ってる

結果: For文等のループ処理が遅くなってしまう



# Treesitterのネイティブサポート



# Treesitterとは？

構文解析ツール

VimのSyntax Highlightは正規表現で行われており、複雑なSyntaxや、動的なSyntaxの判定は行うことができなかった

Treesitterによって文脈にそった構文解析を行うことができ、これによってよりきれいなHighlightができるようになる



# LSP Clientのネイティブサポート



# LSPとは？

Language Server Protocolの略

IDEが必要とする型やメンバーの自動補完、変数やメンバーの定義参照、変数やメンバーの定義参照などサービスとして提供する

VSCodeなどが用いている



# LSP Clientのネイティブサポート

旧Vim、NeoVimでは有志の方が作ったプラグインを用いてLSP Clientを使っていた

v0.5ではこれがネイティブでサポートされたのでより手軽にLSPを使用することができるようになった

しかもLuaで書かれてる、速い(多分)



# NeoVim v0.5は新機能が盛りだくさん！



# でも



# Vimも負けてない



# Vimの新機能



# Vim9Script



# Vim9Script

｢遅いVimScript｣の現状を打破するために作られた新たなVimScript

既存の文法を大規模に改変し、JITコンパイルにも対応

JITコンパイルしないLuaよりも速いらしい



# まとめ



# みんなVim/NeoVimを使おう！