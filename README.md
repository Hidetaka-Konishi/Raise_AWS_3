# Cloud9を使ってアプリケーションをデプロイし、ブラウザ接続する手順
※インストールするパッケージのバージョンはREADME.mdに書かれている

1. ターミナルでGitHubのリポジトリをクローン　```git clone [リポジトリのURL]```
2. rubyをインストール　```rvm install ruby-3.1.2```
3. bundlerをインストール　```gem install bundler:2.3.14```
4. MySQLをインストールする。MySQLの起動が成功したらパスワードを変更する。手順 → [MySQLのインストール](https://github.com/MasatoshiMizumoto/raisetech_documents/blob/main/aws/docs/install_mysql_on_cloud9_amazon_linux_2.md
)

6. yarnをインストールするために```npm install -g yarn```を実行する。yarnがインストールされたら依存関係をインストールするコマンド```yarn install```を実行する。
7. Bundlerをインストールするコマンド```gem install bundler```を実行する。
8. ```cd リポジトリ名```でクローンしたリポジトリのディレクトリに移動したら```bundle install```を実行する。
9. アプリケーションに必要なファイルの設定を行ったら```rails s```でアプリケーションを起動する。
10. Cloud9の「Run」の横にある「Preview」→「Preview Running Application」をクリック。Cloud9の右下にある「Browser」をクリックする。

# Cloud9上で目的のディレクトリに移動するためのコマンド
```pwd```　現在地を把握できる

```ls```　目的のディレクトリに行くためのルートを一覧表示

```cd```　例えば「config」という場所に移動したい場合はcd configと実行する

```cd ..```　現在のディレクトリから一つ前のディレクトリ(親ディレクトリ)に移動できる

# Cloud9で使用しているサーバーの名前を確認する方法
「Gemfile」というファイルの中に使用しているAPサーバーやDBサーバーの名前が書かれている。

# バージョンを調べるコマンド
バージョンを調べるためのコマンドは```[プログラミング言語やサーバー名] --version```のように指定する。例えば、```puma --version```や```ruby --version```といった感じ。

# Cloud9でMySQLサーバーを起動・停止させるコマンド
起動　```sudo systemctl start mysqld```

停止　```sudo systemctl stop mysqld```
