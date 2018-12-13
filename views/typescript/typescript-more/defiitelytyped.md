## 类型定义文件

#### 是什么以及解决什么
* 在typescript中在写代码时候我们可以直接给代码定义类型，但是我们使用的很多库是javascript写的，会报错，所以需要让js库能定义静态类型。
* ts之前提出过 tsd, typings 都已废弃，在2.0时候提出了**DefinitelyTyped**。
* **DefinitelyTyped** 就是让我们吧（*.d.ts）文件发布到npm中，配合编辑器或者插件，检测到js库的竟来类型。