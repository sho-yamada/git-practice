# git研修用リポジトリ

gitの操作に慣れるためのリポジトリです。
基本的な操作をターミナル上で実行し、gitの基本操作を習得してもらうことが目的です。

## 目次

- リモートリポジトリのクローン
- コミットとプッシュ
- コミットの打ち消しとやり直し
- プル
- コンフリクトの解消
- ブランチの作成とマージ

### リモートリポジトリのクローン

```
git clone [URL]
```
上のコマンドを実行し、Githubからgit-practiceリポジトリを取得します。  
※ コマンド実行時にGitHubのIDとPASSの入力を求められます。

### コミットとプッシュ

ローカル環境にクローンしてきたリポジトリ内でファイルの変更を行い、  
その変更内容をコミットしてみましょう。

コミットが完了したら、リモートリポジトリにコミットした内容をプッシュしてください。

```
git add
git commit
```

### コミットの打ち消しとやり直し

「行ったコミットメッセージを修正したい」「修正したファイルをコミットし忘れてしまった」

そんな時はコミットのやり直しを行うことで解決できます。

```
git commit -amend
```

### プル

自分のローカルとリモートの間で差分が生まれてしまった場合に用います。  
（他の人が自分の作業分をリモートにプッシュしてしまった場合など）

プルという動作を行うことで、リモートの変更内容をローカルに持ってくることが出来ます。

### コンフリクトの解消

前述のプルを行った時、自分と他者の作業箇所が重複しているとエラーが起きます。

基本的にGitは両者の変更内容を上手く取り持って保存してくれますが、変更箇所が重複している場合は保存に失敗します。

保存に失敗する理由は「どちらの修正内容を優先して保存するべきなのか」をGit側から判断することが出来ないためです。

こういう場合は、「変更内容をどのように保存するのか」を手動で修正してやる必要があります。

### ブランチの作成とマージ

機能追加、バグ修正・・これらを行う場合は、
masterブランチでそのまま作業を行わずに作業するための専用ブランチを切ることが殆どです。

実際にブランチを切ってみましょう。
```
git checkout -b [branch-name]
```

1. 作業のためのブランチを作る。
2. ブランチ内で作業を終え、問題無い事が確認できたらmasterブランチにマージする。
(問題なしかどうかを判断する基準は場合によって変わる)
3. 次の作業を始める時は、最新のmasterからブランチを切り直す。

基本的には上記の流れで作業を行っていきます。
