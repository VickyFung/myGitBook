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

**注意需要再单独引入组件、安装组件**

`import { Header } from 'mint-ui'Vue.component(Header.name, Header)`
然后在App.vue中放入header
```
<mt-header fixed title="冯慧敏的vue项目"></mt-header>
```



