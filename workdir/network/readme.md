# network構築
## 作成対象
- vpc
- subnet

## vpc
```
# 作成
aws cloudformation deploy --stack-name {stack-name} --template-file network.yml --parameter-overrides $(cat {template.properties})
## sample
aws cloudformation deploy --stack-name shunsuke-nonomura-network --template-file network.yml --parameter-overrides $(cat shunsuke-nonomura-network.properties)

# 削除
aws cloudformation delete-stack --stack-name {stack-name}
```

## 参考
- [CloudFormationを使ってVPCを構築する](https://qiita.com/okubot55/items/b18a5dd5166f1ec2696c)