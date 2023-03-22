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

-it インタラクティブモード
-v ボリューム　ローカルの${PWD}/srcをdocker内/var/wwwに同期する
${PWD}/src に変更を加えると/var/www にも変更が反映される
Dockerfile は CMD ["/bin/bash"]にしておく

```
docker container run -it -p 4567:4567 --name sinatra -v ${PWD}/src:/var/www sample/sinatra:latest
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
