# Docker-cakephp

## 最初に行う設定
+ コンテナを起動・生成
```
docker-compose up -d
```
### コンテナにcomposerをインストール
+ phpコンテナに入ってcomposer 公式ドキュメントにあるコマンドで composer.phar をインストール

```
docker exec -it php /bin/bash
```
```
cd /var/www
```
<br>

【注意】下記４つのコマンドはコピペせず composer 公式ドキュメントにあるコードを使用
> [composer公式ドキュメント](https://getcomposer.org/download/)

```
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
```
```
php -r "if (hash_file('sha384', 'composer-setup.php') === '756890a4488ce9024fc62c56153228907f1545c228516cbf63f885e036d37e9a59d27d63f46af1d4d07ee0f76181c7d3') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
```
```
php composer-setup.php
```
```
php -r "unlink('composer-setup.php');"
```
***
### phpコンテナ内にcakephpをインストール
+ phpコンテナに入ってcakephpをインストール<br>
  ※ cakephpのバージョンは使用環境に応じて変更
```
php composer.phar create-project --prefer-dist cakephp/app:3.9 html
```
+ composer.phar を /var/www/html の中に移動
```
mv composer.phar html
```
+ app.phpのDatasourcesを使用環境に応じて編集、ローカル環境の表示環境を設定

## 新規で案件を追加する場合
### ファイルを追加・編集
+ *projectsディレクトリ*配下に追加する案件を配置
+ *docker-compose.yml*のnginxのところでポートを指定
+ *nginxディレクトリ*下にconfファイルを作成(listenはdocker-composeで指定したポート番号を記載)
***
### Dockerに設定を反映

```
docker-compose up -d
```