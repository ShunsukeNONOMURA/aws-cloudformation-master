# aws cloudformation master
cloudformation で実験する用途のマスタ  
cli実行環境をdockerで作成

## 起動
.envの作成
```
AWS_ACCESS_KEY_ID='YOUR_AWS_ACCESS_KEY_ID'
AWS_SECRET_ACCESS_KEY='YOUR_AWS_SECRET_ACCESS_KEY'
```

端末上で実行
```
# up.sh
docker compose run --rm aws-cli-container /bin/bash

# 起動試験（要S3アクセス権）
root@000000000000:/worker# aws s3 ls

# 終了
exit
```