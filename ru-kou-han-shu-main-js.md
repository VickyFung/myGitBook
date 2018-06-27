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
**1 使用Mint-UI的header组件**
npm装包
import引包
Vue.use安装

**2 注意header等mint-ui的组件**
需要再单独引入组件、安装组件
然后在App.vue中放入header
import { Header } from 'mint-ui'
Vue.component(Header.name, Header)
`<mt-header fixed title="冯慧敏的vue项目"></mt-header>`
注意header被fixed了，脱标了，要给appContainer加一个上padding

##制作tabbar

**1 使用MUI模板**
1)从GitHub上下载压缩包，解压
2)将mui的dist文件夹拷贝到src/lib文件夹下，更改名字为miu
a.src/lib下面存放手动拷贝过来的包
b.node_modules存放的是npm安装的包
3)import ‘./lib/mui/css/mui.min.css’
在examples文件夹中找到自己需要的代码片段，拷贝过来放到html中即可

使用时把a标签换成router-link，把href换成to，把#换成/

**2 注意小图标的问题**

**3 tabbar图标高亮**
删除图标的 mui-active类
在router.js中（我们这个项目在router文件夹下的index.js中）
设置linkActiveClass属性值为 'mui-active'  //覆盖默认的路由高亮类，默认的类是router-link-active

**4 tabbar路由链接实现**
创建四个组件
然后在router.js中导入四个组件，并定义路由规则

##制作轮播图
**1 轮播图组件**
使用mint-ui的swiper组件

注意swiper组件默认高度是0
**2 轮播图数据获取**
- 用vue-resource
 + npm装包
 + import导入
 + Vue.use安装
- 轮播图模拟从服务器拿数据:本地创建一个main.js文件

```
var http = require('http')
var fs = require('fs')
var server = http.createServer()

server.on('request',function(req,res){
  var url = req.url
  if(url === '/'){
	fs.readFile('D:/web/program20180620/myServer/index.html',function(err,data){
			if(err){
				return res.end('not found')
			}
			res.end(data)
		})
		console.log('收到客户端的主页请求了')
	}
	console.log('收到客户端外面的请求了')
})
server.listen(3000,function(){
	console.log('服务器启动成功了，可以通过http://xxx:3000来进行访问了')
})```

- 使用ngrok http 8080，将本机映射到外网，模拟服务器
- 然后nodemon main.js即可
- 注意读取文件中的目录的绝对路径
- 注意项目的端口号不能和服务器端口号一样
 + 通过更改项目的config文件夹下的index.js中的port:4040来更改项目的端口号
 + 这里需要注意，如果你修改后的端口仍然是被其他占用的，name他会给你默认改回8080！！！


- telnet怎么使用

## 跨域请求问题
**1 什么是跨域**
跨域即不同源之间访问，源：协议+域+端口
不同协议（http、https）
不同域名（）
不同端口（）
都叫跨域
**2 跨域访问的几种方式**
- jsonp
 + jsonp就是为了跨域访问存在的
 + 但是jsonp并不能
 + jsonp需要服务端支持，并不是说用了jsonp就能把所有不支持跨域的请求变成可以跨域的。你需要一个服务器环境，然后配置代理转发
- 代理转发
 + www.123.com访问www.123.com/123.php
 + www.123.com/123.php在后端调用www.456.com/456.php
 + 这样就可以绕过浏览器，就不存在跨域问题了
- PHP端修改header
 + 在php接口脚本中加入以下两句
 + header("Access-Control-Allow-Origin:*")//允许所有源来访问
 + header("Access-Control-Allow-Method:POST,GET")//允许访问的方式

