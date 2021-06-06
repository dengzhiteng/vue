[vue.config.js的使用](https://segmentfault.com/a/1190000017008697)

## yarn 
1. 全局安装 Yarn 的最新版本
```
npm install yarn -g
```
- tips1 可能会出现安装失败的情况，这个时候可以以管理员的身份进入终端进行安装

## 创建Vue3.0 项目
- vue create、vue ui、vue init均可以创建vue 项目，本章节介绍通过 vue create 的方式来创建项目

1. 安装 最新版本vue-cli 
```
npm install @vue/cli -g
```
测验方法  
```
vue -V

```

2. 初始化Vue 项目
```
vue creat vue-next-test
```
输入命令后，会出现命令行交互窗口，这里我们选择 Manually select features

```
Vue CLI v4.3.1 
? Please pick a preset
  default (babel eslint)
> Manually select features  
```
随后我们勾选：Router,Vuex，Css Pre-processors 和 Linter/Formatter



## step ref
- setup 函数的用法，可以代替 Vue2 中的 date 和 methods 属性，直接把逻辑卸载 setup 里就可以
- ref 函数的使用，它是一个神奇的函数，我们这节只是初次相遇，要在template中使用的变量，必须用ref包装一下。
- return出去的数据和方法，在模板中才可以使用，这样可以精准的控制暴漏的变量和方法。


## Vue3 的生命周期比较多，我们需要一个个给大家讲。
- setup() :开始创建组件之前，在beforeCreate和created之前执行。创建的是data和method
- onBeforeMount() : 组件挂载到节点上之前执行的函数。
- onMounted() : 组件挂载完成后执行的函数。
- onBeforeUpdate(): 组件更新之前执行的函数。
- onUpdated(): 组件更新完成之后执行的函数。
- onBeforeUnmount(): 组件卸载之前执行的函数。
- onUnmounted(): 组件卸载完成后执行的函数
- onActivated(): 被包含在<keep-alive>中的组件，会多出两个生命周期钩子函数。被激活时执行。
- onDeactivated(): 比如从 A 组件，切换到 B 组件，A 组件消失时执行。
- onErrorCaptured(): 当捕获一个来自子孙组件的异常时激活钩子函数（以后用到再讲，不好展现）。

## Vue2--------------vue3 生命周期 对比
- beforeCreate  -> setup()
- created       -> setup()
- beforeMount   -> onBeforeMount
- mounted       -> onMounted
- beforeUpdate  -> onBeforeUpdate
- updated       -> onUpdated
- beforeDestroy -> onBeforeUnmount
- destroyed     -> onUnmounted
- activated     -> onActivated
- deactivated   -> onDeactivated
- errorCaptured -> onErrorCaptured

## vue3 新增的钩子
- onRenderTracked 
直译过来就是状态跟踪，它会跟踪页面上所有响应式变量和方法的状态，也就是我们用return返回去的值，他都会跟踪。只要页面有update的情况，他就会跟踪，然后生成一个event对象，我们通过event对象来查找程序的问题所在。
- onRenderTriggered
直译过来是状态触发，它不会跟踪每一个值，而是给你变化值的信息，并且新值和旧值都会给你明确的展示出来。


## watch








