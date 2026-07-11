# 「SQL 第2版 ゼロからはじめるデータベース操作」学習用リポジトリ

## docker を使った PostgreSQL の起動方法

```bash
# PostgreSQL のコンテナを起動する
docker run --name sql-zero -e POSTGRES_PASSWORD=password postgres

# PostgreSQL のコンテナに接続する
docker exec -it sql-zero psql -U postgres -d shop
# 初回
docker exec -it sql-zero psql -U postgres -d postgres

# PostgreSQL のコンテナを再起動する
docker start -ai sql-zero

# PostgreSQL のコンテナを削除する
docker rm sql-zero
```

### PostgreSQL のコマンド例

```sql
# データベース一覧
\l
SELECT datname FROM pg_database;

# データベースの作成
CREATE DATABASE shop;

# テーブル一覧
\dt
SELECT table_name FROM information_schema.tables WHERE table_schema = 'public';
```

## フォーマット

### SQLFluff を使った方法

```bash
sqlfluff fix sample.sql
```
