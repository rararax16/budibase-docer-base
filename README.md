# budibase docker 構築

budibaseをローカルに構築するためにベースとなるアプリケーションになります。

# 事前準備
docker-compose.ymlファイルを修正してください

## budibase.environmentの修正
「<secret>」を任意の値に変更してください  
``` yml
    environment:
      JWT_SECRET: <secret>
      MINIO_ACCESS_KEY: <secret>
      MINIO_SECRET_KEY: <secret>
      REDIS_PASSWORD: <secret>
      COUCHDB_USER: <secret>
      COUCHDB_PASSWORD: <secret>
      INTERNAL_API_KEY: <secret>
```

## db.environmentの修正
「<secret>」を任意の値に変更してください  
``` yml
    environment:
      MYSQL_ROOT_PASSWORD: <secret>
      MYSQL_DATABASE: <secret>
      MYSQL_USER: <secret>
      MYSQL_PASSWORD: <secret>
      TZ: Asia/Tokyo
```

## db.volumesの修正
「<secret>」を任意の値に変更してください  
``` yml
- ~/docker-volume/mysql/<secret>:/var/lib/mysql
```

# budibase 起動
docker を起動し、下記のコマンドを実行してください。  
起動後、数分後 「 http://localhost:8080/ 」 にアクセスするとbudibaseにアクセスできます
``` bash
docker compose up -d
```

# budibase 停止
``` bash
docker compose down
```



