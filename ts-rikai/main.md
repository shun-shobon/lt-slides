---
theme: default
paginate: true
headingDivider: 1
---

# 最強の型を目指して

## ~TSのConditional Typesを理解する~



# 自己紹介

- 名前: SHUN/しゅん
- 学年: 高専新3年生
- 得意言語: TypeScript、JavaScript、Haskell、など
- 得意分野: Webがチョットデキル、TSの型芸、CI/CD
- Twitter: @shun_shobon
- GitHub: @shun-shobon



# 今日話すこと



# TypeScriptの型はすごい



# とはいえ



# TypeScriptの型は難しい



# 三大TSの難しい型

- Mapped types
- Conditional types
- Template literal types



# 今回はこれらの中でも特に***†やばい†***Conditional typesを理解しようというコンセプトです



# 事前準備

さっきの2つの型を話す前にTSならではの型について解説します

- Union types
- Literal types

なお、これから話すTSのサンプルコードはすべてTSの設定を`strict: true`(厳密な型チェックを有効にする)にしているものとします



# Union types

日本語では共用体型とか言われるやつ

複数の型の｢どちらかを取りうる型｣を定義することができる

```typescript
let value: string | number = 123;

console.log(value * 5); // Error!

if (typeof value === "number") {
  console.log(value * 5); // OK!
}

value = "foo"; // OK!
value = true; // Error!
```



# Literal types

値そのものを型として用いることができる

```typescript
type Foo = "foo" | "bar";

let foo: Foo = "foo"; // OK!
foo = "bar"; // OK!
foo = "baz"; // Error!
```



# 事前準備終了



# 本題



# Conditional types

一言でいうと、｢型レベルif｣

構文は`T extends U ? V : W`

｢TがUに代入可能ならばVを、そうでなければWという型になる｣⇒三項演算子みたいなもん

**TSで一番やべえ型**

```typescript
type Foo = "foo";

type Bar = Foo extends string ? "true" : "false";

const bar: Bar = "true"; // OK!
const baz: Bar = "false"; // Error!
```



# え？これだけ？



# そんなことはない



#  Type inference in Conditional types

**ジェネリクスに存在しない型を作り出せる機能**

`T extends U ? V : W`のUの部分に`infer X`と書くことで、`V`の部分で新たに作り出した`X`を使用することができる

```typescript
type ArrayItem<T> = T extends Array<infer U> ? U : never;

type Foo = Array<string>;

type Bar = ArrayItem<Foo>; // stringになる
```



# 例

Next.jsで用いられる動的ルーティングされる箇所のみをUnion Typesとして抽出

```typescript
type QueryUnion<TPath extends string, TQueries extends string = never> =
  TPath extends `/[${infer Query}]/${infer Other}` ? QueryUnion<`/${Other}`, TQueries | Query>
  : TPath extends `/${infer _}/${infer Other}` ? QueryUnion<`/${Other}`, TQueries>
  : TPath extends `/[${infer Query}]` ? TQueries | Query
  : TPath extends `/${infer _}` ? TQueries
  : never;

const path = "/[foo]/bar/[baz]/qux";

type Queries = QueryUnion<typeof path>;
// => "foo" | "bar"
```



# 例

TSの型のみで作られたもの

- Brainf\*\*k
- 自然数演算
- SQL文パーサ
- GraphQL文パーサ



# こんな難しい型なんて使いこなせない…



# パズル感覚で学習できたら楽しくない？



# Type Challenge

![](https://raw.githubusercontent.com/type-challenges/type-challenges/master/screenshots/logo.svg)

- TSの様々な型機能を駆使して、出されたお題に対して最適な答えを探す
- 例: Union typesからTuple typesを作る、再帰を用いてObject typeのすべてをReadonlyにするDeepReadonlyを作る、カリー化を型レベルでする、C言語のprintfっぽいものを型レベルで作るなど
- 答え合わせはテストケースを用いて自動でやってくれます
- 公式から正しい答えが提供されるわけではないので他の人の答えも見て、自分だけの答えを探そう！



# まとめ

## 型芸は楽しいのでみんなもやろう！

