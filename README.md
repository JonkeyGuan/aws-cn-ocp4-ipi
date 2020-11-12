# Red Hat OpenShift Container Platform v4 on AWS China

通过以下方式可以在AWS中国区 通过IPI方式安装 OCP4

## 需要准备的资源
1. AWS中国区域的帐号。
2. Red Hat 账号，用于下载installer和pull secret。
3. 已备案的域名。

## 1. 安装配置aws cli和jq

首先需要在您用于运行安装程序的电脑上安装并配置aws cli。具体步骤请参考[AWS文档](https://docs.amazonaws.cn/cli/latest/userguide/cli-chap-install.html)。

配置aws cli，添加两个profile. 详细步骤参考[aws cli文档](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-configure-profiles.html).
* china: 配置AWS中国区管理员的AK/SK，区域设置为cn-northwest-1.

安装命令行json工具jq。具体步骤请参考[jq wiki](https://github.com/stedolan/jq/wiki/Installation)。

## 2. 新建VPC

设置CLUSTER_NAME环境变量. 

```bash

export CLUSTER_NAME=myocpcluster

```


按照需要更新[vpc参数文件](parameters/1_vpc_params.json). 然后执行下面的命令新建VPC。

```bash

./scripts/1_create_vpc.sh

```

## 3. 通过openshift-install 命令安装OCP4

参考以下链接 [install](https://docs.openshift.com/container-platform/4.6/installing/installing_aws/installing-aws-vpc.html)



