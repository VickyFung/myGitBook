#新闻列表页
- 使用MUI的media-list模板
- v-for+key循环渲染，注意src和key属性前面要加:

**1 新闻最底部显示不全**
- 因为APP.vue的头部和尾部都脱标了，所以需要加padding就好了


**2 日期格式化**
- 日期默认格式是毫秒
- 需要定义全局过滤器来对日期进行格式化
- 需要用到格式化时间的插件：moment插件
 + npm安装
 + import引入
- 使用过滤器的方法
 + `{{dateStr | dateFormat}}`
 + 其中dateStr是需要被格式的日期， dateFormat是过滤器名称
- 定义过滤器的方法

```
Vue.filter('dateFormat',function(dateStr,pattern = "YYYY-MM-DD HH:mm:ss"){
  moment(dateStr).format(patern)
})
```
**3 数据渲染**

#新闻详情页

**1 全局配置**
- 项目API根路径

`Vue.http.options.root = 'http://xxxx'`
- post请求格式

`Vue.http.options.emulateJSON = true`


