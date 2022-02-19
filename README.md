# aws-sfn-statemachine-samples


# 準備
以下は、自身のPC(Mac/Intel)にインストールされている状態であるとする。

[参考](https://long-crustacean-3ba.notion.site/VSCode-RemoteContainer-0a24ac829347457c899132a1b3fdf593)

* [VSCode](https://azure.microsoft.com/ja-jp/products/visual-studio-code/)
* (VSCode plugin)[Remote - Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
* [DockerDesktop](https://docs.docker.jp/docker-for-mac/install.html)



# 構築環境
※詳細は `.devcontainer` を参照のこと
 
## OS
* amazonlinux2

## AWS
* [aws-cli](https://docs.aws.amazon.com/ja_jp/cli/latest/userguide/install-cliv2-linux.html)
* [sam-cli](https://docs.aws.amazon.com/ja_jp/serverless-application-model/latest/developerguide/serverless-sam-cli-install-linux.html)
* [rain](https://aws-cloudformation.github.io/rain/)
* [cfn-lint](https://github.com/aws-cloudformation/cfn-lint)
* [localstack](https://github.com/localstack/localstack)


## タスクランナー
* [go-task](https://taskfile.dev/#/)

## 備考
* .devcontainerのDockerfileをheredoc対応させたため、dockerのバージョンが古いとビルドできないかもしれません。
