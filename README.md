### docker-compose イメージのビルド

```
docker-compose build
```

### docker-compose コンテナの作成と起動

```
docker-compose up
```

### docker-compose コンテナを停止・削除

```
docker-compose down
```

### docker-compose コンテナの一覧を表示

```
docker-compose ps
```

### docker-compose ログを表示

```
docker-compose logs
```

### docker-compose コンテナを作成してコマンド実行

```
docker-compose run <サービス> <コマンド>
```

### docker-compose 起動中のコンテナにコマンドを実行

```
docker-compose exec <サービス> <コマンド>
```

## 起動手順

1. rails new

```
docker-compose run web rails new . --force --database=mysql
```

2. rails new により/src/Gemfile が書き換わるので再 build

```
docker-compose build
```

3. db の設定変更
   /src/config/database.yml の
   default の password(docker-compose.yml での設定 password) と host(docker-compose.yml での設定 services 名) を以下に変更

   - password: password
   - host: db

4. db の作成

```
docker-compose run web rails db:create
```
