#加入购物车动画初步实现
**1 小球的位置和样式**
- 小球最好直接放在最根部的div里面，后面小球运动的时候只能在他的父盒子显示，如果放在了某个小盒子里，那么显示的动画过程是不完整的
- 小球用定位固定位置，并z-index提高层级

**2 绑定点击事件**
- 给小球一个v-show="flag"属性
- 绑定点击事件，flag取非

**3 钩子函数实现半程动画**
- 把小球用transition包起来
- 给transition绑定四个动画钩子事件
```
<transition 
    @before-enter="beforeEnter" 
    @enter="enter" 
    @after-enter="afterEnter">
    <div class="cart-ball" v-show="ballFlag">
    </div>
</transition>
```
- 定义四个钩子事件
```
beforeEnter(el) {
    el.style.opacity = 1;
    el.style.transform = "translate(0, 0)";
},
enter(el, done) {
    el.offsetWidth;
    el.style.transform = "translate(58px, 234px)";
    el.style.transition = "all 1s cubic-bezier(.49,-0.21,1,.53)";
    done()
},
afterEnter(el) {
    this.ballFlag = !this.ballFlag;
}
```

**4 cubic-bezier贝塞尔曲线**
- 默认全程时间为t，全程路线为s
- x轴
 + 在原点的时候，代表前半程用时0.5t，匀速运动
 + 往正方向移动，代表前半段路程用时增加，前半段慢，后半段加速
- y轴
 + 往正方向移动，前半段快，后半段减速