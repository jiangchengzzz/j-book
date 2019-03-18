## 从0搭建一个weex项目

> 大概过程是按照 [前辈的搭建方式](https://weex.apache.org/zh/solution-detail/detail.html?spm=a2c7j.-zh-community-.0.0.43bdc8eetOL8EN&id=40)我这边记录一下 搭建过程中遇到那些问题，和一些我觉得的重点
--------

#### 准备工作
1. 新建项目工程
> mkdir create-weex
cd create-weex
npm init -y  

2. **安装依赖**
* 由于weex-loader暂不支持webpack4，所以只能安装3.x版本webpacck-dev-server对应安装2.x
> npm i webpack@3.x webpack-dev-server@2.x -D
* babel
npm i babel-loader babel-core babel-preset-env -D
touch .babelrc
.babelrc中写入
```
{
  "presets": ["env"]
}
```
* vue 
> npm i vue -s
npm i vue-loader autoprefixer postcss-plugin-weex postcss-plugin-px2rem weex-vue-precompiler  -D
* weex-loader  作用是把.vue文件转化为native端使用的.weex.js
>npm i weex-loader -D
* weex-vue-render Vue DSL 的 Web 渲染器， 它在 Web 上实现了 Weex 的内置组件和内置模块
>npm i weex-vue-render -S
