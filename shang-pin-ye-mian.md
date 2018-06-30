# 组件中的布局问题
- 组件中的布局和组件中的样式一样，都只能有一个根
- 问题：这是组件自带的属性还是因为使用了SCSS？

#编程式导航
**1 导航(路由)的几种方式**
- 通过a标签的href导航
- 通过js进行路由导航，就叫做编程式导航

**2 编程式导航的几种方式**
- this.$router.push(‘home’+id)
- this.$router.push(path:’home’+id)
- this.$router.push({name:”goodsinfo”,params:{id}})