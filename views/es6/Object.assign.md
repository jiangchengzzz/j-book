# 记Object.assign

## 基础内容
  Object.assign是ES6的接口,
  * 写法
```
    Object.assign(target, ...sources)
    target: 目标对象（必须是对象）。
    sources: 源对象（可多个）。
    返回值：目标对象。
```
  * 用法
  1. 主要是用来合并多个对象，将多个源对象合并到目标对象，并返回目标对象。如果出现对象里面的的key重复，后合并的对象的value会覆盖前合并的。
  2. 例：
  ![](./images/Object.assign1.png)
  作用就是把之前，表单的数据合并这些数据，如果有改变的就替换没有就增加。
## 注意
  1. Object.assign接受的第一个参数必须是对象，不是就会自动转换成对象，如果是null或者undefined就会报错。
  2. Object.assign的拷贝是浅拷贝，当接受的value是对象时，只是一个引用。

### 深入了解
[点击这里](https://blog.csdn.net/qs8lk88/article/details/79018481)