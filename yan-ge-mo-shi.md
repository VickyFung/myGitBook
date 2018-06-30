#什么是严格模式

#启用严格模式

#移除严格模式
**1 需要移除的情况**
- 比如我们import引入.js文件时，.js文件中可以使用了非严格模式的callee、caller、arguments等属性，这时就会报错
- 这种情况下我们可以考虑修改引入的js文件，但是禁用严格模式更方便

**2 如何移除**

- 装包：`npm i babel-plugin-transform-remove-strict-mode`
- 配置（三种方式）：
    + .babelrc
    + vue-cli
        - `$ babel --plugins transform-remove-strict-mode script.js`
    + node API


- 详见：[移除严格模式](https://github.com/genify/babel-plugin-transform-remove-strict-mode)