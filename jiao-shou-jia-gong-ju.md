#项目开始前

##环境和工具准备

###安装nodejs
* nodejs官网下载安装包，一直点击下一步即可完成安装
* 安装完成后，配置环境变量，然后打开cmd，输入`node -v`查看node版本
* 安装成功后，即可使用npm包管理工具了

###安装url镜像
**nrm的使用**
* cmd中运行`npm i nrm -g`，全局安装nrm
* `nrm ls`，查看当前所有可用的镜像源地址
* `nrm use taobao`，使用淘宝镜像

**安装淘宝镜像**
* `npm i -g cnpm --registry=https://registry.npm.taobao.org`
* 安装完成后`cnmp -v`检查是否安装成功
* 安装成功后即可使用cnpm包管理工具了

**安装webpack**
* `npm i webpack -g`

**安装vue-cli**
* `npm i vue-cli -g`
* `vue -V`检查是否安装成功