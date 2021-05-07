---
title: GitPressのコードブロック機能
date: 2021-05-07
excerpt: GitPressのコードブロック機能を試してみました。
---

## コードブロック機能
GitPressではCode-Knackというブラウザ上でコードをオンライン実行できるevaluatorを使っており、
下記のような一般的なコードブロックを書くことでGitPressから簡単に実行できるようです。

### 例
```java
public class GitPress {
  public static void main(String[] args){
    for(int i = 0; i < 10; i++){
      System.out.Println("Hello GitPress");
    }
  }
}
```
