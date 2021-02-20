<!--
 * @Author: 蒋承志
 * @Description: file content
 * @Date: 2021-02-19 16:50:15
 * @LastEditTime: 2021-02-19 17:51:07
 * @LastEditors: 蒋承志
-->

# vue3.0 源码学习记录

## 为什么要学习

- 额，估计就是因为感觉自己太菜了，暂时有一些空余时间。
- 前段时间写vue3.0发现有很多新的实现方式以及好玩的东西，所以想看看实现，加上以前一直有计划，所以现在就搞起来。

## 学习源码计划

    看了好几天了发现没啥头绪，搞得让人头大，所以还是找个视频学起来把，可以省去一些奇怪的问题出现的时间

首先就抄一波说明，各个模块包含的东西

- compiler-core:编译
- compiler-dom:dom 相关代码
- compiler-sfc:单文件编译部分
- compiler-ssr:服务端渲染编译相关
- reactivity:Vue3 响应式部分,Proxy 就在这里面
- runtime-core:运行时与创建实例相关代码
- runtime-dom:运行时与 dom 相关代码
- runtime-test:内部测试代码(如果大家想详细了解各部分功能，可以参考一下这个文件夹)
- server-renderer:服务端渲染
- shared:Vue3 工具库，通用方法
- size-check:Vue3 简单的一个应用，用来测试代码体积
- template-explorer:内部使用的编译文件浏览工具
- vue:Vue3 主入口文件

![3.0结构]('../img/pic-1.png', '3.0结构')

那么就开始计划一下学习

1. 首先肯定是先研究看一下从创建到渲染的过
2. 然后再分块进行学习
