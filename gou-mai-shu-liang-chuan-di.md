# 购买数量监视
- 当点击购买数量的+或-的时候，或者当手动输入购买数量值的时候，都会改变购买数量，如果逐个添加事件，则代码会非常多
- 可以用change事件（类似click）监视购买数量的变化，当值变化时，触发函change函数
- change事件仅仅适用于，`<input>、<textarea>、<select>`三种标签
- `<input @change = 'countChanged'/>`

# 子组件向父组件传值
- 子组件通过$emit，调用父组件的方法，并将要传递的值作为方法的实参传给父组件
- `countChanged(){
this.$emit('父组件方法名', '要传递的实参')}`
