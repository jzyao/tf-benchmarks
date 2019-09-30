# 用例： TF benchmarks

## 安装ks
```
wget https://github.com/ksonnet/ksonnet/releases/download/v0.13.0/ks_0.13.0_linux_amd64.tar.gz
tar -vxf ks_0.13.0_linux_amd64.tar.gz
cd ks_0.13.0_linux_amd64
sudo cp ks /usr/local/bin
```

## 安装kubectl 

## 安装tf-operator
```
APP_NAME=my-kubeflow
ks init ${APP_NAME}
cd ${APP_NAME}

ks registry add kubeflow github.com/kubeflow/kubeflow/tree/master/kubeflow #可以安装本地registry

ks pkg install kubeflow/common
ks pkg install kubeflow/tf-training

ks env list
ks prototype list
ks generate tf-job-operator  tf-job-operator
ks apply default
```

## 修改 tf-operator 镜像
docker pull jzdoris/tf-operator 

## 跑例子
```kubectl apply -f job-gpu.yaml```

用例 1. 1 ps  1 worker  1 GPU node

用例 2. 2 ps  2 worker  2 GPU node

用例 3. 2 ps  4 worker  2 GPU node
