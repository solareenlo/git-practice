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
