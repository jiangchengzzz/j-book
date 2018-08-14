# react的渲染方式

### 基础内容
　　react是通过reder函数来渲染的，render函数可以接受两个参数：

  - 1. 你要渲染的内容，也就是一段html代码。
  - 2. 你要渲染的位置，一般一个react应用都**只有一个**根元素。  

例如：
```
const element = <h1>Hello, world</h1>;
ReactDOM.render(
  element,
  document.getElementById('root')
);
```
  **注意**：一般在开发中只会调用一次render函数，调用之前会对之前的dom和现在要更改的dom进行比对，只更新更改的部分

### 原理
    以后再写吧