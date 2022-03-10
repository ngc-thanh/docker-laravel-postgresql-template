[win] $ tree
.
┣ docker/
┃    ┣ docker-entrypoint-initdb.d/ // PostgreSQLのDBセットアップ用ディレクトリ
┃    ┃
┃    ┣ pgadmin4/ // pgAdmin4のデータ格納用ディレクトリ
┃    ┃
┃    ┣ Dockerfile
┃    ┃
┃    ┗ php.ini // PHP設定ファイル
┃ 
┣ prj/ // ソースコード格納用ディレクトリ
┃
┗ docker-compose.yml

docker-entrypoint-initdb.dに「.sql」「.sh」「.sql.gz」などのファイルを置いておくと、PostgreSQLイメージからコンテナを生成・起動する際に実行してくれます。

pg_dumpallやpg_dumpで出力したスクリプトも、拡張子が「.sql」であれば実行可能です。pg_dumpallについても記事を書いたので、ご参考になれば幸いです。

`
docker-compose down -v

docker-compose build --no-cache

docker-compose up -d
`

`docker exec -it web bash

composer create-project --prefer-dist laravel/laravel .

chmod 777 -R bootstrap/cache/

chmod 777 -R storage/

http://localhost/
`

`
docker exec -it web bash
psql -h postgres -U default -d postgres
`

`
pgAdmin
http://localhost:8000/
id: root
password: root
name: postgres
hostname: postgres
port: 5432
database: postgres
user: default
password: secret
=> save
`