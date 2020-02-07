# 社内Git勉強会

## 勉強会のゴール

- 基本的なgitの操作に慣れる
- 実際に文言修正pull requestを投げられるようにする

TODO: 井上くんに「なんすか？めんどくさいっす自分で直してください」って言われなくなるみたいないらすと屋の画像を作る

## 対象者

- ソフトウェア開発のPM
- 駆け出しエンジニア

## 必要なもの

* [VSCode](https://azure.microsoft.com/ja-jp/products/visual-studio-code/)

コマンドラインでやりたい人は `terminal` に `git` を入れてください。

今一番ポピュラーなテキストエディタは ~`vim`~ `VSCode` なので入れとけばいいと思います。

他のGitクライアント使っても同じことができます。

* [SourceTree](https://www.sourcetreeapp.com/)
* [GitHub Desktop](https://desktop.github.com/)
* [Git Kraken](https://www.gitkraken.com/download/mac)

今回はVSCodeのGitの機能を使おうと思います。

## そもそもGitってなんなの？

難しく言うと、分散型レポジトリシステム。

簡単に言うと、複数人でできるバージョン管理システム。

## 抑えとくべき用語/コマンド

最低限これさえあればなんとかなる。

### 用語

1. レポジトリ ...
2. ローカル ... 自分のPCのこと
3. ブランチ ...
4. チェックアウト ...
5. コマンドライン ... 黒い画面の文字列しかないやつ

### 基本

1. `git clone` ... レポジトリをローカルにダウンロードしてくる
2. `git status` ... 自分が変更したファイルが見れる
3. `git add` ... 自分が変更したファイルを
4. `git commit` ... `add` で選択したファイルにコメントを付けて保存
5. `git push` ... ローカルにある最新の情報をGitHubにアップロードする
6. `git pull` ... GitHub上にあるレポジトリの最新の情報を取ってくる

### ブランチ操作

1. `git branch` ... ブランチの操作をする
2. `git checkout` ... ブランチを切り替える


## gitコマンドを入れて、ssh keyをGitHubに登録する
### コマンドの導入

```
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
$ brew install git
$ git --version
git version 2.25.0
```

### ssh keyを作成してGitHubに登録する

```

```

## まずはレポジトリをcloneする

[このレポジトリ](https://github.com/UUUM/git-study) をクローンする

```
$ cd ~/Desktop
$ git clone git@github.com:UUUM/git-study.git
$ cd git-study
```

VSCodeでクローンした `UUUM/git-study` を開いてみる。

## issueを立ててみる

url: [https://github.com/UUUM/git-study/issues](https://github.com/UUUM/git-study/issues)

先に立ててみた

![issue.png](./img/issue.png)

## branchを切ってみる
### VSCodeの場合

![branch_1.png](./img/branch_1.png)

![branch_2.png](./img/branch_2.png)

### コマンドラインでやる場合

```
# 01.mdを更新したい場合
$ git branch
* master
$ git checkout -b feature/update-01_md
Switched to a new branch 'feature/update-01_md'
$ git br
* feature/update-01_md
  master
```

## 作業をする

issueで割り当てられたファイルを適当に編集してみる。

## commitしてpushをする

### VSCodeの場合

![commit.png](./img/commit.png)

### コマンドラインでやる場合

`01.md` のファイルを編集した場合こういう表示になる
```
$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
    modified:   01.md

no changes added to commit (use "git add" and/or "git commit -a")


$ git add 01.md
$ git commit -m "ここにコミットメッセージを書く"
$ git push origin HEAD
```

## pull requestを作り、mergeしてみる

TODO: 書く

## masterを最新にする

### VSCodeの場合

TODO: 書く

### コマンドラインでやるなら
```
$ git branch
* feature/add-01
  master
$ git checkout maser
$ git pull
```

## 参考記事

- [GitHubで共同開発のためのチュートリアル](https://qiita.com/takeokunn/items/5bc499121a21f8c5b990)
- [サルでもわかるGit入門](https://backlog.com/ja/git-tutorial/)
