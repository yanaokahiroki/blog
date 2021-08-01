---
title: 別リポジトリの最新版を取り込む
date: 2021-07-31
excerpt: 別リポジトリの最新版を取り込む
---

# 別リポジトリの最新版を取り込む

業務の中で担当しているパッケージのリポジトリとは別のリポジトリの最新版を取り込むことがあったので記事にします。

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

これで準備が完了です。

