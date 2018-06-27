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
 + 但是如果接口没有实现对jsonp请求的包装，jsonp也不能实现跨域请求
 + jsonp需要服务端支持，并不是说用了jsonp就能把所有不支持跨域的请求变成可以跨域的。你需要一个服务器环境，然后配置代理转发
- 代理转发
 + www.123.com访问www.123.com/123.php
 + www.123.com/123.php在后端调用www.456.com/456.php
 + 这样就可以绕过浏览器，就不存在跨域问题了
- PHP端修改header
 + 在php接口脚本中加入以下两句
 + header("Access-Control-Allow-Origin:*")//允许所有源来访问
 + header("Access-Control-Allow-Method:POST,GET")//允许访问的方式

