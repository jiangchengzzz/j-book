# react的常用

## 事件处理
  **react的事件处理和DOM相似，只是语法上有一点不同**
  1. 事件绑定属性的命名是驼峰形式的.
  2. 传入的事件用{}包起来的函数.
  3. react中阻止默认事件，不能像DOM中那样触发函数然后return false。必须要使用e.preventDefault().

## 条件渲染
  **根据不同数据的状态改变控制某块内容是否渲染**
  和vue一样的用法，只是会改变一些写法,没有了v-if这种东西，直接用if-else这种去写在需要渲染的代码中

## 列表
  **其实和vue差不多，也是写法变了，可以直接在html中使用循环，然后注意key的重要性**  

## 表单
  #### 受控组件  
    react提出了一个以前没见过的概念，受控组件，**input, textarea, select**等，读完文档后的感觉：其实就是一表单组件例如ipt其内容我们在写入的时候，其实是被监控的，输入显示的内容其实是监控处理过后的内容，所以说，当我们想对我们输入的内容显示就行更改，可以直接在onChange函数中写。比如我们想输入的字母全部大写：
    ```
    class NameForm extends React.Component {
      constructor(props) {
        super(props);
        this.state = {value: ''};
        this.handleChange = this.handleChange.bind(this);
        this.handleSubmit = this.handleSubmit.bind(this);
      }
      handleChange(event) {
        this.setState({value: event.target.value.toUpperCase()});
      }
      handleSubmit(event) {
        alert('A name was submitted: ' + this.state.value);
        event.preventDefault();
      }
      render() {
        return (
          <form onSubmit={this.handleSubmit}>
            <label>
              Name:
              <input type="text" value={this.state.value} onChange={this.handleChange} />
            </label>
            <input type="submit" value="Submit" />
          </form>
        );
      }
    }
    ```
    现在想想，其实用vue，应该也是同样的原理，没去看vue源码，只是在应用中的感觉。
    注：<input type="file">不是一个受控组件

## 状态提升
  #### 状态提升是一个概念，按照我读文档的理解：
    简单来说就是，当我们需要通过某种方式更改一个状态，但是这个状态同时被另外一个组件使用，并且另外的组件也会根据当前状态更改，我们就需要将这个状态提升到最近的父组件，然后通过更改状态时触发事件，去更改父组件的状态，这样我们可以同时去更改两个组件展示不同内容。
  #### 思考
  这个的用处？
  1. 按照理解，最大的作用应该是当我们有多个组件需要共用这个状态，但是又在不同的组件的时候，我们就放在父组件。

  2. 弊端
    但是如果我们有很多组件都需要用到这个状态，并且组件层级或者说组件树比较乱，比较复杂的时候，用状态提升就比较麻烦了。
    所以呢，这就是**redux**的用处了，嗯感觉是这样


## 组合继承
  #### 提起来有点懵逼，和当时学习js继承的时候一样，但是其实也挺容易的
1. 首先把**包含关系**， 这个呢其实相当于vue中的组件内得<slot name="body"></slot>这种，表示把要写的东西放到这个组件的这里。
2. 表示办法： 
  * 第一种就是直接 {props.children},你在组件中写入的内容会放到写这个的位置。
  * 还有一种就是自定义，当你组件有多个入口的时候，就需要用到，详情，大概就是，定义多个子组件，把子组件已对象的方式传给你要显示的子组件然后子组件通过props.点点点 ，嗯再去读文档吧。