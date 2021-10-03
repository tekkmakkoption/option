```
# 参考
## VSCodeとGithubを連携してできること
https://breezegroup.co.jp/202102/vscode-github-windows/
## フォークしたリポジトリを最新化する方法
https://qiita.com/Nossa/items/ace2ab802adc85f86b20
## とほほのGit入門
https://www.tohoho-web.com/ex/git.html
## Visual Studio Code の git 連携機能と git コマンドについて
https://qiita.com/satokaz/items/4660ce57ca8eb456a096
## これで完璧! 図解でわかるgit rebaseの2つの使い方!
https://www.sejuku.net/blog/71919

# 基本の流れ
- VSC起動し、リモートを指定
  - https://github.com/tekkmakk/mysite
- 下部の左ボタン押下しブランチを選ぶ

# 最新情報取得
git fetch

# 引き落とし
git pull
# 最新化～再作成
git pull --rebase

# GitHubのフォーク元のリポジトリをリモートブランチに追加する
git remote add upstream https://github.com/フォーク元オーナー名/フォーク元リポジトリ名.git
git remote add upstream https://github.com/tekkmakkoption/option

# フォーク元の master ブランチの変更差分をフェッチます。
# ※upstream/master に保管されます
git fetch upstream

# masterブランチをチェックアウトしフォーク元の差分をマージします。
git checkout master
git merge upstream/master
## deployの場合
git checkout deploy
git merge upstream/deploy

# 最後に自分の修正ブランチに master ブランチを取り込みます。コンフリクトが出たら解決します。
git checkout 自分の修正ブランチ
git merge master

# 新規ブランチ作成
git switch -c new_branch	# ローカルリポジトリにブランチを作成する(新しい書き方)
git switch new_branch		# ブランチを切り替える(新しい書き方)
git push -u origin new_branch	# 新ブランチをリモートリポジトリにプッシュする

# 他の修正を繋ぎなおす
git rebase [つなぐ元にするブランチ名]
git rebase [つなぐ元にするハュシュ]

# 特定ハッシュまで戻す
git reset ハッシュ

# ローカル修正を一時よける
git stash save		# 現在の変更を一時的に退避する
git stash list		# 退避したスタッシュの一覧を表示する
git stash pop			# 退避していたスタッシュを元に戻す
```
