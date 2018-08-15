# react的组件

## 基础
　　react程序是由一个个组件组合来的，组件化的思想在react体现的淋漓尽致，之前一直用vue，体会并没有这么的深刻。
* 组件的定义
  react组件的定义有两种方式：
    - 1. 函数定义组件，向其中传入一个props对象，里面包含着，我们向其传入的内容，返回一个react元素。例：
    ```
      function Welcome(props) {
        return <h1>Hello, {props.name}</h1>;
      }
    ```
    - 2. 用es6的chass定义一个类,我理解的字面意思是，定义一个class（必须以大写字母开头） 继承React.Component。例：
    ```
      class Welcome extends React.Component {
        render() {
          return <h1>Hello, {this.props.name}</h1>;
        }
      }
    ``` 
    注: 目前看到的必须注意的点：
    1. class必须以大写开头。
    2. 所有的props只读，子组件不能更改它（官方文档特别声明，还没体会到）。  