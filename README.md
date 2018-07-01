# 创建本地项目

**使用脚手架工具创建项目**

参考推荐：[使用vue-cli构建项目
](https://www.jianshu.com/p/1626b8643676)


#本地项目上传到GitHub之前

**1 git init之前的准备**
- README.md文件：对项目的简单说明文件，不可缺少
- .ignore：指定在项目上传时忽略的文件，如图表示忽略node_modules文件夹，因为该文件夹较大，不推荐上传，如果丢失我们只需要再次安装就可以了
![](/assets/搜狗截图20180701143946.png)

**2 初始化（在git bash中执行）**
- git init：在项目根目录生成一个.git文件夹
- git status：查看文件状态
- git add .：添加到跟踪（暂存区）
- git commit -m “这里写你此次提交的备注信息”：提交到本地仓库
- git push：提交到远程仓库（和远程仓库建立关联之后可以提交）





# GitHub注册和仓库创建

**1 注册**

略

**2 设置公钥**
- 在本地电脑账户的.ssh文件夹中查看公钥(id_rsa.pub)
![](/assets/搜狗截图20180701145804.png)
- 如果没有.ssh文件夹，需要重新生成公钥：
 + 在cmd终端输入`ssh-keygen -t rsa`即可生成

**3 创建仓库**

![](/assets/创建远程仓库.png)

**4 全局配置用户身份**

- `git config --global user.name "username"`
- `git config --global user.email "youremail@example.com"`


**5 和本地项目关联**

- 在项目根目录执行git bash here
- 和远程仓库关联：`git remote add origin https://github.com/用户名/远程仓库名.git`
- 项目上传：`git push -u origin master`
- 上传后即可在GitHub上看到自己的项目







