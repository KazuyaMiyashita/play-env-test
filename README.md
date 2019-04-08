# playframeworkで環境変数を利用するテスト

* `application.conf`で環境変数を読み込むことができる
* コントローラで利用するには、`Configuration`をDIする
* 環境変数は`~/.bashrc`に直接書き込むか、direnvを利用する
  * 今回はdirenvを利用した。
* `$ brew install direnv`
* `~/.bashrc`の末尾に下記をを追加した
  * `eval "$(direnv hook bash)"`
* `$ direnv allow .`
  * (レポジトリごとに一回行えば良い?)
* macはデフォルトでターミナルを開いた時にbashrcが読み込まれないので、
  下記を`~/.bash_profile`に追加した

```
if [ -f ~/.bashrc ]; then
  . ~/.bashrc
fi
```

* `.envrc`というファイルに必要な環境変数を設定する
* **`.envrc`を.gitignoreする。**
  * ローカルのグローバルな設定で行うと良いと思う
  * * `git config --global core.excludesfile $HOME/.gitignore_global`


./gitignore_global

```
# direnv
.envrc

# Scala (VSCode + Ensime)
/.ensime
/.ensime_cache/*
/ensime-langserver.log
/pc.stdout.log*~

# others
.DS_Store
```