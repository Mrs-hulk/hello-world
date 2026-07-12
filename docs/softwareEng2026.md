---
layout: page
title: "software Eng. lecture note
permalink: /docs/softwareEng2026
---

# CI/CDの実践-Github Pages

## Github Pagesの概要
Github Pagesは，Github上にあるリモートリポジトリの内容をWebページとして公開できるサービスのことである．Markdownファイルを作成するだけでJekyllが自動的にHTMLへ変換し，ホームページを公開できる．ホームページの公開はCI/CDにより自動化される．

## Github Pagesの設定手順
- リポジトリ名の変更

Settingタブから **Hello-World**を **<ユーザー名>.github.io**へと変更する．

- Jekyllの設定

Settings→Pages→Build and deployment→Sourceから「Github Action」を選択する．そのままGithub Pages Jekyll→configureを実行し，デフォルトのままymlファイルをコミットする．

ここからはgithubフローに則り，devブランチでCodespaceを用いてWeb公開用のディレクトリ *docs*を作成し，その中で 

`jekyll new --skip-bundle .`

`bundle install`

を実行する．Jekyllが作成した.gitignoreファイルに 

`Gemfile.lock`
を追加する．

- _config.ymlファイルの設定

タイトルやベースURL，公開URLなどを自身のものに修正する．

- index.markdownの変更

このファイルに，トップページのタイトルや内容を記入する．また， `[リンクのタイトル](ファイル名)`と追記することでdocsディレクトリ内にあるYAMLを設定した.mdファイルをリンクとして追加することが出来る．