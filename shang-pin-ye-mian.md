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
- this.$router.push({name:”组件名字”,params:{id}})

#点击跳转指定页面
**1 上级页面传入id到url**
```
getGoodsDetail(id){
 this.$router.push({path:'/home/goodslist/'+id}) 
}
```
**2 下一级页面获取id**
- `url_id: this.$route.params.id`
- 获取id之后，按照id渲染该页面组件内容即可

#轮播组件提取
**1 父子组件传值**
- 父组件传值
 + `<swiper :swiperList="goodsList" :isfull="false"></swiper>`
 + swiperList是传给子组件的属性，是载体
 + goodsList是父组件的data数据，是内容
- 子组件取值
 + `props: ["swiperList","isfull"]`
 + props和data平级
 + props是一个数组，专门用来获取父组件传来的值
 
 **2 轮播图图片宽度的问题**
 - 不同的父组件引用轮播图时，传入的图片大小不一样，所以有的想要width：100%，有的想要自适应
 - 父组件向子组件传递一个属性参数，来告诉子组件要不要width：100%
 - 即上面的isfull属性
 - 然后在子组件的样式中，给img加一个full的类，并在样式中定义.full
  + `<img :class="{'full': isfull}" :src="item.img" />`
  + `.full {width: 100%}`
  
 **3 图片水平垂直居中**
 ```
 img {
	position: absolute;
	top:0;
	bottom:0;
	left:0;
	right:0;
	margin:auto;
}
```

#商品详情页面
**懒加载效果**
- 需要用到mint-ui的Lazyload
- `<img v-lazr="http" >`
- `img[lazy=”loading”]{}`设置懒加载转圈圈图标的样式
 
 
