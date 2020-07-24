---
title: " React 学习\t\t"
tags:
  - 其他
id: '81'
date: 2018-07-18 16:00:57
---

**1.**用npm新建react项目 **2.JSX：**JavaScript 的语法扩展。JSX 用来声明 React 当中的元素。JSX本身是一种表达式，在JSX可以使用表达式。 **3.组件（props）：**无论是使用[函数或是类](#%E5%87%BD%E6%95%B0%E5%AE%9A%E4%B9%89/%E7%B1%BB%E5%AE%9A%E4%B9%89%E7%BB%84%E4%BB%B6)来声明一个组件，它决不能修改它自己的props。 定义一组件：

*   使用JavaScript函数；
*   使用[ES6 class](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Classes)来定义一个组件可以组合组件，也可以提取组件(组件可复用性)；

**4.render() 方法**：调用render() 方法来改变输出，更新UI。 **5.将函数转化为类**：（为类添加局部状态 将this.prop.date修改为this.state.date）

*   创建一个名称扩展为Component 的[ES6 类；](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Classes)
*   创建一个叫做render()的空方法；
*   将函数体移动到render() 方法中；
*   在render() 方法中，使用 props 替换 props；
*   删除剩余的空函数声明；

**6.构造函数：**（来初始化状态） 在构造函数中定义super 关键字，调用当前对象从父类继承过来的对象方法。 **7.生命周期：**在类中可以添加生命周期方法（生命周期勾子） 我们可以在组件类上声明特殊的方法，当组件……时，来运行下面相应代码。 **8.setState()**：可以来更新组件局部状态（状态更新可能是异步的） **9.事件处理：**（用驼峰式写法） this.handClick= this.handClick.bind(this) bind()方法会创建一个新函数，当这个新函数被调用时，它的this值是传递给bind()的第一个参数； 向事件处理程序中传参，通过 bind 方式向监听函数传参，在类组件中定义的监听函数，事件对象 e要排在所传递参数的后面 **10.条件渲染：**元素变量、与运算符、三目运算符 **11.列表组件**：[map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)方法可以遍历数组 Keys：一个元素的key最好是这个元素在列表中拥有的一个独一无二的字符串。通常，我们使用来自数据的id作为元素的key；当元素没有确定的id时，你可以使用他的序列号索引index作为key。 **12.表单：**受控组件（其值由React控制的输入表单元素称为“受控组件） **13.组合**（建议使用组合而不是继承来复用组件之间的代码）

*   包含关系：组件使用children属性将子元素直接传递到输出
*   特殊实例：在 React 中，这也是通过组合来实现的

**14.React Router：**（路由）

*   path参数：添加路径参数；
*   Link：<Link to\='/'\>Home</Link\>（必须为绝对路径）