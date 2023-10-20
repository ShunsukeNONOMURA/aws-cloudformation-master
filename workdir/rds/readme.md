# RDS構築

## インスタンス
```
# 作成
aws cloudformation deploy --stack-name {stack-name} --template-file ec2.yml --parameter-overrides $(cat {template.properties})
## sample
aws cloudformation deploy --stack-name shunsuke-nonomura-rds --template-file rds.yml --parameter-overrides $(cat shunsuke-nonomura-rds.properties)

# 削除
aws cloudformation delete-stack --stack-name {stack-name}
## sample
aws cloudformation delete-stack --stack-name shunsuke-nonomura-rds

# インスタンスタイプ確認
aws rds describe-orderable-db-instance-options --engine rds-postgresql --engine-version 15.2 --query 'OrderableDBInstanceOptions[].[DBInstanceClass,StorageType,Engine,EngineVersion]' --output table --region ap-northeast-1
```

## 参考
