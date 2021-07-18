---
title: リポジトリにpush権限がなくて詰まった話
date: 2021-07-05
excerpt: リポジトリにpush権限がなくて詰まった話
---

# リポジトリにpush権限がなくて詰まった話

チーム開発で新規参画した場合にリポジトリのCloneをし、実装し、PRを出そうとしたところ下記のエラーに阻まれました。

```sh
$ git push origin HEAD
ERROR: Repository not found.
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```

## 原因

リポジトリに対して権限がなかったため。
リポジトリオーナーにCollaboratorとしてリポジトリに追加してもらうことで解消しました。

## 参考

* [【Git】cloneはできたのにpushでRepository not found.となるエラー](https://www.mtioutput.com/entry/git-push-repositorynotfound)

* [GitHubで特定のリポジトリを複数人で共有する方法](https://reasonable-code.com/github-collaborators/)
