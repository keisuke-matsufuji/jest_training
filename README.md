# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm test`

単体テストの実行

- Jest

  - テストランナー(テスト用スクリプトを package.json に設定)
  - test(function.js で使用)
    - テストケース(test の代わりに it を使うことも可能)
  - describe(function.js で使用)
    - テストスイートで、テストケースをまとめて管理
    - テストケースは必ずテストスイートに含まれるわけではなく、テストケース単体の場合もある。
  - create-react-app を使用している場合、Jest は標準でインストールされる。

- React Testing Library

  - ReactDOM を用いないレンダリング
    - render メソッド。引数にコンポーネントを取り、オブジェクトを返却する。  
      返却されたオブジェクトの中の、クエリ関数を用いて DOM 要素を取得
      Star.test.js で使用
  - イベントの発火
    - DOM 要素を取得したときに、イベントが設定されている DOM であれば、`fireEvent.click("DOM要素")`で発火可能。  
      Checkbox.test.js で使用

### `npm test -- --coverage`

全体のコードのうち、どれだけの行数がテストされたかを計測してパーセンテージで表すことを、`コードカバレッジ`という。  
Jest もコードカバレッジのレポート機能を持っており、Istanbul を使ってこれを実現している。

Jest でコードカバレッジの機能を利用するには、--coverage フラグをつけて`npm test`を実行する。

```
npm test -- --coverage
```

なお、`--coverage`の前に`--`をつけているのは、jest に対してフラグを指定するため。  
`--`がないと、jset ではなく npm に対するパラメータとして扱われてしまう。

テスト実行時、console にカバレッジの結果が出力される。

また、`./coverage/lcov-report/index.html`というファイルが作成され、詳細なレポート結果をブラウザで確認することができる。
