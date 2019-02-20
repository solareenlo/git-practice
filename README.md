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
