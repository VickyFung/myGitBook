**ES6为我们提供了模板字符串，语法使用反引号`。模板字符串具有以下三个优点：**

- 多行文本
- 字符串中插入变量
- 字符串中插入表达式

#基本语法

**模板字符串和 ES5的字符串的声明一样。**
```
// ES5
var name = 'xixi';
console.log(name);// xixi

// ES6
let name4ES6 = `一步`;
console.log(name4ES6);// 一步
```

#多行文本

**在Jquery 盛行的年代，我们经常会拼接 html 片段再进行节点替换。写一段 ES5的代码大家体会一下：**
```
var str = '<html>'
+ '<div>啦拉拉</div>'
+ '<div>xixixi</div>'
+ '</html>';
console.log(str);// <html><div>啦拉拉</div><div>xixixi</div></html>
```

**ES6支持多行文本，上面的代码实现起来就容易多了。**



```
let str4ES6 = `<html>
    <div>啦拉拉</div>
    <div>xixixix</div>
</html>`;

console.log(str4ES6);
```

#可以插入变量或表达式
```
// ES5
var name = 'xixi';
var age = 27;
var info = 'my name is ' + name + ' , age is ' + age + '.';
console.log(info);// my name is xixi , age is 27.
```

**ES6的模板字符串实现起来就容易好多。关键语法`${}`，其中可以插入任何的 js 表达式。**
```
let name = 'xixi';
let age = 27;

let info = `my name is ${name}, my age is ${age}. just a test ${1 + 10}!`;
console.log(info);// my name is xixi, my age is 27. just a test 11!
```