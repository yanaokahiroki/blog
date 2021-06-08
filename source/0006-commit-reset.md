---
title: Your branch is ahead of ‘origin/ブランチ名’ by 〇 commitsと出たら
date: 2021-06-08
excerpt: Your branch is ahead of ‘origin/ブランチ名’ by 〇 commitsと出たら
---

# Your branch is ahead of ‘origin/ブランチ名’ by 〇 commitsと出たら

リモートブランチに対してローカルのブランチが進んでいて、
その変更内容をpushしてないことが原因で表示されます。

下記2種類の方法で解決することができます。

## 1.ローカルブランチの内容が正しくこれをリモートに反映させたいパターン

```bash
git pull origin ブランチ名
```

## 2.リモートブランチに強制的に合わせるパターン

```bash
git reset --hard origin/ブランチ名
```

## 参考

[GitでYour branch is ahead of ” by 〇 commitsと出た場合の対処](https://www.nblog09.com/w/2019/01/24/git-ahead/)