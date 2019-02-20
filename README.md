# git-practice

## gitの構成
- 作業ディレクトリ
- ステージングエリア（インデックス）
- リポジトリ（ローカル, リモート）

## gitの設定
```bash
# gitへユーザー名を登録
git config --global user.name "solareenlo"

# gitへメールアドレスを登録
git config --global user.email "solareenlo@test.com"

# gitを色づける
git config --global color.ui true

# commitしたときのエディタをvimに設定する
git config --global core.editor vim

# gitの設定一覧を見る
git config -l

# gitのhelpを見る
git config --help
```

## 初めてのcommit
```bash
# gitの初期化
git init

# 作業ディレクトリからステージングエリアへ
git add index.html

# ステージングエリアからリポジトリへ
git commit
# タイトルとか変更内容を書いて, :wq

# 変更のlogを見る
git log
```

## gitのlogを見る
```bash
# logをコンパクトに見る
git log --oneline

# logと共に変更内容も見る
git log -p

# どのファイルが変更なったかを見る
git log --stat
```

## 現在の状態を把握する
```bash
# 現在の状態を見る
git status

# ファイルの変更を無かったことにする
git checkout -- index.html
```

## 差分を確認する
```bash
# ファイルの差分を見る
git diff

# ステージングされたファイルの差分を見る
git diff --cached
```

## gitでのファイル操作
```bash
# 現在のディレクトリ以下全部のファイルをaddする
git add .

# gitでのファイル削除
git rm index.html

# gitでのファイル移動
git mv index.html
```

## gitの管理に含めない方法
```bash
# .gitignoreファイルを作り, その中にgitに含めないファイルを記述する
vim .gitignore
*.log

# .gitignoreがある場所から遡ってはignoreされない.
# ので, サブディレクトリだけ.gitignoreしたい場合は, サブディレクトリ内に.gitignoreを入れておく.
```

## 直前のcommitを変更する
```bash
# 1つcommitする
git commit -m 'コミットを1つ追加'

# 直前のcommitを上書きする
vim index.html
git add .
git commit --amend
```

## 過去のバージョンに戻る（１）
```bash
# 作業ディレクトリもステージングエリアも直前のcommitへ戻す
git reset --hard HEAD

# 2つ前のcommitに戻る
git reset --hard HEAD^

# 指定したidにcommitを戻す
git reset --hard hash値(最低7桁)
```

## 過去のバージョンに戻る（２）
```bash
# commit変更したけど, やっぱり変更前のcommitに戻りたいときは
git reset --hard ORIG_HEAD
# ORIG_HEADには前回取り消されたHEADの情報が1つだけ入っている.
```

## branchを使う
```bash
# 現在のbranchを確認する
git branch

# 新しいbranch hogeを作成する
git branch hoge

# hoge branchに移動する
git checkout hoge
git branch

# master branchに戻る
git checkout master
git branch
```

## branchをmergeする
```bash
# master branchにhoge branchをmergeさせたい
git checkout master
git merge hoge

# いらなくなったhoge branchを削除する
git branch -d hoge

# masterにmerge済みのbranchを確認する
git checkout master
git branch --merged

# masterにまだmergeしていないbranchを確認する
git checkout master
git branch --no-merged

# 作業途中でmergeしたときに, まだcommitしたくないときは, stashを使って一時的に変更内容を退避させる.
git stash save 'コメント'

# stashで退避させた情報の一覧表示
git stash list

# 退避させるたびに, この一覧の上に退避データが積み上がっていく.
# 対比した内容を取り出すには
git stash pop
# 引数をつけない場合, listで表示された一番上の内容が取り出される.
```
