# syntax = docker/dockerfile:1.3-labs
FROM amazonlinux:2
LABEL maintainer "reona.hoshino <dev.reona.hoshino@gmail.com>" 

# some tools
RUN <<EOS
    yum update -y
    yum install -y tar gzip git vim epel-release curl unzip sudo jq wget sqlite-devel
    yum groupinstall -y "Development Tools"
    yum install -y gcc openssl-devel bzip2-devel libffi-devel
EOS

RUN <<EOS
    amazon-linux-extras install -y docker
EOS

# some tools
RUN <<EOS
    yum update -y
    yum install -y tar gzip git vim epel-release curl unzip sudo jq wget
EOS

RUN <<EOS
    amazon-linux-extras install -y docker
EOS


RUN yum clean all

# sam cli
RUN <<EOS
    curl -L https://github.com/aws/aws-sam-cli/releases/latest/download/aws-sam-cli-linux-x86_64.zip -o samcli.zip
    unzip samcli.zip -d sam-installation
    sudo ./sam-installation/install
    rm -rf samcli.zip
EOS

# aws cli
RUN <<EOS
    curl -L https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip -o awscliv2.zip
    unzip awscliv2.zip
    sudo ./aws/install
    rm -rf awscliv2.zip
EOS

# rain 1.2.0
RUN <<EOS 
    curl -L https://github.com/aws-cloudformation/rain/releases/download/v1.2.0/rain-v1.2.0_linux-amd64.zip -o rain.zip
    unzip rain.zip -d rain
    mv rain/rain-v1.2.0_linux-amd64/rain usr/bin/rain
    rm -rf rain.zip rain
EOS

# go-task
RUN sh -c "$(curl --location https://taskfile.dev/install.sh)" -- -d -b /usr/local/bin

ENV SHELL=/bin/bash

# git補完
RUN <<EOS
    curl  https://raw.githubusercontent.com/git/git/master/contrib/completion/git-prompt.sh -o /root/git-prompt.sh
    curl  https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash -o /root/git-completion.bash
EOS

# git-flow
RUN <<EOS
    curl -L https://github.com/nvie/gitflow/raw/develop/contrib/gitflow-installer.sh | bash
EOS
