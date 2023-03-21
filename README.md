### docker image の作成

-t タグ付け

```
docker image build -t sample/webrick:latest .
```

### docker image の確認

```
docker image ls
```

### docker container の起動

-p ポート指定
--name container の名前付け

```
docker container run -p 8000:8000 --name webrick sample/webrick:latest
```

### docker container の停止

```
docker container stop webrick
```

### docker container の削除

```
docker container rm webrick
```

### docker container の状況確認

```
docker container ls -a
```

### docker log を確認

```
docker container logs webrick
```

### docker コマンドを実行

```
docker container exec webrick ruby -v
```

### docker お掃除(使っていないイメージ、コンテナを削除)

```
docker system prune -a
```
