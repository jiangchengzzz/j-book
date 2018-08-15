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
