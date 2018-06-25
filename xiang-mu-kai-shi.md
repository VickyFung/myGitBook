#1.git init之前
- .gitignore文件：node_modules、.git、.idea、.vscode
- README.md文件
- LICENSE：开源协议www.zhihu.com/question/19568896

#2.git init初始化
- git init：在项目根目录生成一个.git文件夹
- git 全局设置用户名和密码
 + git config --global user.name “”
 + git config --global user.email “”
- git status：查看文件状态
- git add .：添加到跟着（暂存区）
- git commit -m “init my project”：提交到本地仓库
- git push：提交到远程仓库
- 注意：如果出现commit报错不认识本地用户的时候，在.git文件夹下的config文件最后，加这一段内容
```
[user]
email = "18817392508@163.com"
name = "VickyFung"
 ```