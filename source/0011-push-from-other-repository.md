---
title: 別リポジトリの最新版を取り込む
date: 2021-07-31
excerpt: 別リポジトリの最新版を取り込む
---

# 別リポジトリの最新版を取り込む

業務の中で担当しているパッケージのリポジトリとは別のリポジトリの最新版を取り込むことがあったので。

まずは下記の`git remote`コマンドで現在追加されているリモートリポジトリを確認します。
これは実際の`blog`リポジトリにおける実行結果です。originという名前で`blog`リポジトリがリモートリポジトリとして追加されていることがわかります。
originという名前はgitがデフォルトもつ名前です。

```sh
$ git remote -v
origin  git@github.com:yanaokahiroki/blog.git (fetch)
origin  git@github.com:yanaokahiroki/blog.git (push)
```

現在のリモートリポジトリの名前とそのアクセス先が分かったところで次のコマンドです。
次は取り込みたい別のリポジトリをリモートリポジトリとして追加します。
そして`git remote`で確認するとother-repositoryという名前で追加されていることを確認できます。

```sh
$ git remote add other-repository git@github.com:yanaokahiroki/blog-test.git

$ git remote -v
origin  git@github.com:yanaokahiroki/blog.git (fetch)
origin  git@github.com:yanaokahiroki/blog.git (push)
other-repository    git@github.com:yanaokahiroki/blog-test.git (fetch)
other-repository    git@github.com:yanaokahiroki/blog-test.git (push)
```

これで準備完了です。

リモートリポジトリとして追加した`blog-test`リポジトリの最新mainブランチから
`blog`リポジトリのother-repository-latestとしてブランチを新たに切ります。
(ここでは旧checkout構文ではなく新switch構文を使っています。)

参考：[switchコマンド](https://git-scm.com/docs/git-switch)

```sh
$ git switch -c other-repository-latest other-repository/main
Branch 'other-repository-latest' set up to track remote branch 'main' from 'other-repository'.
Switched to a new branch 'other-repository-latest'
```

上のコマンドを実行すると`other-repository-latest`ブランチに移動します。
この新ブランチは`blog-test`リポジトリの最新版から切っているのでそのまま`blog`リポジトリへとpushします。

```sh
$ git push origin HEAD
...文章は省略...
```

あとはGitHub上でPull Requestを作成し、`blog-test`リポジトリでの変更内容を`blog`リポジトリに反映して問題ないか確認、マージ。
(コンフリクトが発生していた場合には適宜解消します。)

これで完了です。
