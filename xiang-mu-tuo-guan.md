#可以将项目上传到远程仓库，如GitHub、码云等
>此处以GitHub为例

##已有项目：
 a)cd vue10
 b)git remote add origin https://gitee.com/用户名/项目名.git
 c)git push -u origin master

##没有项目
a)mkdir vue10（项目名称）
b)cd vue10
c)git init
d)touch README.md
e)git add README.md
f)git commit -m “”
g)git remote add origin https://……
git push -u origin master

##如果push的时候有版本冲突
[解决办法](https://www.cnblogs.com/code-changeworld/p/4779145.html)