# Cloud9を使ってアプリケーションをデプロイし、ブラウザ接続
※インストールするパッケージのバージョンはREADME.mdに書かれている。

1. PowershellでGitHubのリポジトリをクローン　```git clone [リポジトリのURL]```
2. rubyをインストール　```rvm install ruby-3.1.2```
3. bundlerをインストール　```gem install bundler:2.3.14```
4. MySQLをインストールする。MySQLの起動が成功したらパスワードを変更する。手順 → [MySQLのインストール](https://github.com/MasatoshiMizumoto/raisetech_documents/blob/main/aws/docs/install_mysql_on_cloud9_amazon_linux_2.md
)
5. gemをインストール 　```bundle install```
6. ```cd [リポジトリ名]```でアプリのプロジェクトディレクトリに移動。
7. サンプルファイルをコピーして、自分の環境に合わせて設定値を変更　```cp config/database.yml.sample config/database.yml```
8. アプリに使用しているデータベースにログインするときのパスワードを`config/database.yml`ファイルの`password`に入力する。
9. データベースサーバーの設定ファイルに移動　`less /etc/my.cnf`
10. socketのパスをコピーして、`config/database.yml`の`socket`をコピーしたものに書き換える。
11. yarnをインストール　```npm install -g yarn```
12. プロジェクトのセットアップと初期化　```bin/setup```
13. ImageMagickソフトウェアパッケージをインストール　```sudo yum install -y ImageMagick```
14. アプリケーションサーバーの起動　```bin/cloud9_dev```
15. Cloud9の「Run」の横にある「Preview」→「Preview Running Application」をクリック。
16. `Blocked host`というエラーが発生するので、そのエラー文に表示されている`config.hosts << "ec2-34-239-115-7.compute-1.amazonaws.com"`をコピーして`config`→`environments`→`development.rb`ファイルの末尾に書き込む。
17. Ctrl + C でサーバーをストップして、```bin/setup```で再度実行する。
18. 「Browser」をクリックすることでアプリが表示される。

# Cloud9上で目的のディレクトリに移動するためのコマンド
```pwd```　現在地を把握できる

```ls```　今いるディレクトリに存在するディレクトリとファイルを一覧表示

```cd```　例えば`config`というディレクトリに移動したい場合は`cd config`と実行する

```cd ..```　現在のディレクトリから一つ前のディレクトリ(親ディレクトリ)に移動できる

# Cloud9で使用しているサーバーの名前を確認
`Gemfile`というファイルの中に使用しているAPサーバーやDBサーバーの名前が書かれている。

# バージョンを調べるコマンド
バージョンを調べるためのコマンドは```[プログラミング言語やサーバー名] --version```のように指定する。例えば、```puma --version```や```ruby --version```といった感じ。

# Cloud9でMySQLサーバーを起動・停止させるコマンド
起動　```sudo systemctl start mysqld```

停止　```sudo systemctl stop mysqld```
