# EC2構築

## 鍵
```
# ssh key のペアを作成するスクリプト
aws ec2 create-key-pair --key-name {keyname} --query 'KeyMaterial' --output text > {keyname.pem}
chmod 400 {keyname.pem}
## sample
aws ec2 create-key-pair --key-name shunsuke-nonomura-ec2-dev --query 'KeyMaterial' --output text > shunsuke-nonomura-ec2-dev.pem

# 確認する場合
aws ec2 describe-key-pairs --key-name {keyname}

# 削除する場合
# aws ec2 delete-key-pair --key-name {keyname}
```

## インスタンス
```
# 作成
aws cloudformation deploy --stack-name {stack-name} --template-file ec2.yml --parameter-overrides $(cat {template.properties})
## sample
aws cloudformation deploy --stack-name shunsuke-nonomura-ec2-dev --template-file ec2.yml --parameter-overrides $(cat shunsuke-nonomura-ec2-dev.properties)

# 削除
aws cloudformation delete-stack --stack-name {stack-name}
```

## 参考
- [AWS CloudFormationでEC2を構築](https://qiita.com/tyoshitake/items/c5176c0ef4de8d7cf5d8)