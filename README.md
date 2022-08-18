# github-cli-test

## リポジトリ作成

```zsh
# README作成してから、first commitまで
$ mkdir github-cli-test
$ cd github-cli-test/
$ git init
$ touch README.md
$ echo '# github-cli-test' > README.md
$ git add .
$ git commit -m ':tada: first commit'
$ git branch -M main

# リポジトリ作成〜最初のpush
$ gh repo create github-cli-test --description ':octocat: GitHub CLIのテスト' --public
$ git remote add origin https://github.com/kyoruni/github-cli-test.git
$ git push -u origin main
```

## issue

```zsh
# 作成
$ gh issue create --title 'テスト' --body 'これはテストです'
$ gh issue create --title 'hoge' --body 'fuga'

# 確認
$ gh issue list

Showing 2 of 2 open issues in kyoruni/github-cli-test

#2  hoge     about 1 minute ago
#1  テスト    about 1 minute ago

# コメント
$ gh issue comment 1 --body 'コメントのテストです'
```

## p-r

```zsh
# p-r用のブランチ作って、適当に変更 -> push
$ git checkout -b pr-test
$ echo '## テスト' >> README.md
$ git add .
$ git commit -m '#1 :pencil: README修正'
$ git push origin HEAD

# p-rを作成してみる
$ gh pr create --title 'p-rのテスト' --body 'これはテストです'

# マージしてみる
$ gh pr merge 3

? What merge method would you like to use? Create a merge commit
? Delete the branch locally and on GitHub? Yes
? What's next? Submit

# issueを閉じる
$ gh issue close 1
```
