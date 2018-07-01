#实现初步动画效果
- 把要动画的部分用transition包起来
`<transition mode="out-in"></transition>`

- 定义动画样式

```
.v-enter {
	opacity: 0;
	transform: translateX(100%);
}
.v-leave-to {
	opacity: 0;
	transform: translateX(-100%);
	position:absolute
}
.v-enter-active,
.v-leave-active {
	transition: all 0.5s ease;
}

```
# 解决动画效果存在的问题
**1 动画时候的滚动条**
- 原因：开始滚动时app容器中相当于有两个组件，导致内容变成两倍宽，所以出现了横向滚动条

- 解决：给容器一个溢出隐藏：overflow-x:hidden
- 注意：只能加X方向的隐藏

**2 out-in效果的缺点**
- out-in模式让切换显得不流畅，用户体验不好
- 可以给v-leave-to加一个position:absolute，使移出的盒子脱标