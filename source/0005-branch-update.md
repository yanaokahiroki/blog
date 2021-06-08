---
title: 作業中ブランチで最新のmaster(main)を取り込む
date: 2021-06-08
excerpt: 作業中ブランチで最新のmaster(main)を取り込む
---

# 作業中ブランチで最新のmaster(main)を取り込む
チーム開発のリポジトリで作業中のfeatureブランチにいるとき、
他の人の習性が必要で最新のmaster(main)リモートブランチを取得したいことがあります。

その場合には下記の方法で可能です。

## 前提
```
git branch
  master
* feature/fix_something
```

## 1.ブランチの移動が必要なパターン
ブランチを移動する手間があるため少々面倒です。

```
# masterブランチへ移動
git switch master

# masterを更新
git pull origin master

# 作業中ブランチへ戻る
git switch feature/fix_something

# 作業中ブランチへmasterを取り込む
git merge --no-ff master
```

## 2.ブランチの移動がいらないパターン
作業中ブランチにいたままたった2つのコマンドで最新のmasterブランチを取り込むことができます。
```
# originを更新
git fetch origin

# 作業中ブランチへmasterを取り込む
git merge --no-ff origin/master
```

## 参考
[[Git]作業中ブランチに居ながら最新の master を取り込む](https://qiita.com/tommy_aka_jps/items/211c3f6ef961a066a4b7)