# terraformer (既存クラウドからterraformを生成する)

## 環境

terraformのインストール

```
$ brew install terraform

もしくは

$ tfenv install
```

terraformerのインストール

```
$ brew install terraformer
```

## クレデンシャル付与

AWSCLIを使用しても構いません。
「AdministratorAccess」ポリシーをアタッチした IAM ユーザのアクセスキーを前提とします。

```
$ export AWS_ACCESS_KEY_ID=xxxxxxxxxxxxxxxxx
$ export AWS_SECRET_ACCESS_KEY=yyyyyyyyyyyyyyyyyy
$ export AWS_DEFAULT_REGION=ap-northeast-1
```

## 初期化

```
$ echo 'provider "aws" {}' > init.tf
$ terraform init
```

## vpcとSubnetを出力してみる
terraformer import aws --resources=vpc,subnet --connect=true --regions=ap-northeast-1
```