## Hyperledger Fabric 国密补丁

用于Hyperledger Fabric项目支持国密算法，目前在V1.4.1版本上，测试通过

cryptogen工具配套支持, fabric-CA没有测试过

发现flyinox/fabric-sm-patch 中 HASH函数，还是用的SHA256，目前替换为SM3

当前版本采用非插件方式

### 准备条件
---
* 可以编译fabric的主机环境，如ubuntu或者osx

* 安装git环境

* 拉取并且切换到所需要的fabric版本

### 安装步骤
---


在fabric主目录下

* git clone https://github.com/kmadmin/fabric-sm-patch.git

* git am ./fabric-sm-patch/fabric-sm-patch

* git apply ./fabric-sm-patch/fabric-sm3-patch

* make [docker | native]

  使用make编译国密版native或者docker镜像

  推荐使用docker镜像方式，其中自带bccsp密码插件

 

