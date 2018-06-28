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
}
.v-enter-active,
.v-leave-active {
	transition: all 0.5s ease;
}

```
# 解决动画效果存在的问题
**1 动画时候的滚动条**
- 原因：开始滚动时app容器中相当于有两个组件，导致内容变成两倍宽，所以出现了横向滚动条

-解决：给容器一个溢出隐藏：overflow:hidden