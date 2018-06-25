#import引包
首先在入口函数main.js中import引入所需要的包（前提是在npm中已经装过，也就是在node_modules文件中存在的包）

一些必须的包：
import Vue from 'vue'
import router from './router'

#import引组件
然后import引入相关的组件
import App from './App'
./后面的App是组件的名字，体现在App.vue中：
export default {
name: 'App'
}

#制作首页

##首页分析
首页可分为header+中间组件+tabbar三部分
![](/assets/搜狗截图20180625185410.png)

##制作header
使用Mint-UI
npm装包
import引包
Vue.use安装

**注意header等mint-ui的组件**
需要再单独引入组件、安装组件
然后在App.vue中放入header
import { Header } from 'mint-ui'
Vue.component(Header.name, Header)
`<mt-header fixed title="冯慧敏的vue项目"></mt-header>`

##制作tabbar

<使用MUI
1)从GitHub上下载压缩包，解压
2)将mui的dist文件夹拷贝到src/lib文件夹下，更改名字为miu
a.src/lib下面存放手动拷贝过来的包
b.node_modules存放的是npm安装的包
3)import ‘./lib/mui/css/mui.min.css’
在examples文件夹中找到自己需要的代码片段，拷贝过来放到html中即可

使用时把a标签换成router-link，把href换成to，把#换成/
**注意小图标的问题**

tabbar图标高亮
在router.js中（我们这个项目在router文件夹下的index.js中）
设置linkActiveClass属性值为 'mui-active'  //覆盖默认的路由高亮类，默认的类是router-link-active

tabbar路由链接实现
创建四个组件
然后在router.js中导入四个组件，并定义路由规则

