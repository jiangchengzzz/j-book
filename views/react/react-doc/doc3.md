# react的生命周期

## 基础
**之前用vue，体会到了生命周期的好处，站在对比的角度看看react的生命周期有什么不同**
*  **state**
    看官方文档出现了一个以前没见过的，局部状态**this.state**,研究发现其实这个state就相当于vue中的data
    注意:
    1. 修改state中初始化的数据时候，需要调用this.setState()方法。
    2. 因为 this.props 和 this.state 可能是异步更新的，你不应该依靠它们的值来计算下一个状态。
        例如：
        ```
        this.setState({ // 这样的更新状态的方式也许会不会成功
            counter: this.state.counter + this.props.increment,
        });
        ```
        要修复它，请使用第二种形式的 setState() 来接受一个函数而不是一个对象。 该函数将接收先前的状态作为第一个参数，将此次更新被应用时的props做为第二个参数：
        ```
        this.setState((prevState, props) => ({
            counter: prevState.counter + props.increment
        }));
        ```
* componentDidMount 
    这个是当组件输出插入到DOM时候出发的钩子，感觉相当于vue中的mount
* componentWillUnmount
    当组件从DOM中被移除是后调用，感觉相当于vue中的beforedistory

....这个基础教程就讲了这两个。。后再补充吧