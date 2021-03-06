## 一．	项目启动
### 1.	安装vue命令行工具
    1.1 npm install –g vue-cli 安装cli脚手架
    1.2 vue init webpack my-project
    1.3 npm install 安装项目内依赖
    1.4 npm run dev启动服务
## 二．vue的基础知识
    1. 双向绑定，页面上绑定的输入会同步到JS代码里，反之也是，利用v-model
    2. Vue重要选项
    2.1 data数据字段，在在同一个vue文件里可以使用this取值
    2.2 methods方法字段，
    2.3 watch 监听字段
    3. Vue模板指令
        3.1 模板渲染v-text、v-html、{{}}
        3.2 模块控制隐藏v-if（直接不显示dom元素） 、v-show（通过display-none）
        3.3 循环渲染模板 v-for
        3.4 事件绑定 v-on 
        3.5 属性绑定 v-bind，可以简写为:class=”{red:isred}”,当为对象时，为布尔值，数组时为data字符串
## 三．组件间通信
    1. props 用于注册组件间通信的组件，只用于父组件向子组件传数据，在子组件中添加props选项
    2. vue中component注册时可以是大写，但是写标签时应当为小写和中横线，即驼峰改为蛇形命名
    3. 子向父传值，需要在子组件中使用$emit定义父组件中的事件名，并将自己的值A赋值给父组件指定事件函数的参数B，再将参数B赋值给父组件的注册的值C，最后在父组件中处理数据C
## 四．知识点：
    1. 挂载点，标签ID等，vue只处理挂载点的内容
    2. 模板 ：数据展示
    3. 实例：Vue实例，指定挂载点
    4. 实例为实例化vue，指定挂载点，挂载点下处理数据，展示内容
    5. vue组件中模板部分只能有一个父组件
    6. computed：计算属性
    7. vue中直接改变数组的值没有办法触发数据更新视图，需要使用类似push等vue的封装方法或者改变引用
    
## vuex
action->mutation->view
mutation: 不能直接调用mutation，需要使用commit
- mutation都有一个字符串的事件类型(type)和一个回调函数(handler)
- mutation都是同步事务
```javascript
const store = new Vuex.Store({
  state: {
    count: 1
  },
  mutations: {
    increment (state) {
      // 变更状态
      state.count++
    }
  }
})
store.commit('increment', 10)
```
action:
Action提交的是mutation，而不是直接变更状态。
Action可以包含任意异步操作。
Action通过store.dispatch方法触发
```javascript
const store = new Vuex.Store({
  state: {
    count: 0
  },
  mutations: {
    increment (state) {
      state.count++
    }
  },
  actions: {
    increment (context) {
      context.commit('increment')
    }
  }
})
store.dispatch('increment')
```
action和mutation支持同样的载荷方式和对象方式进行分发
```javascript
// 以载荷形式分发
store.dispatch('incrementAsync', {
  amount: 10
})

// 以对象形式分发
store.dispatch({
  type: 'incrementAsync',
  amount: 10
})
```
