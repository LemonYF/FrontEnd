## 踩过的坑
### 普通的开发过程中可能遇到的问题 （记录一下）
    1. vue中直接改变数组的值没有办法触发数据更新视图，需要使用类似push等vue的封装方法或者改变引用
    2. 非父子组件传值： 总线（bus/发布订阅模式/观察者模式）机制。 使用Vue.prototype.bus = new Vue()创建bus属性，在子组件中使用this.bus.$emit('change')，并且mounted的时候监听bus的change事件 this.bus.$on('change')，但是要保存作用域，作用域会改变
    3. 如果想在vue中获取dom元素，使用ref获取
    4. 对象和数组每次置为空后，相当于改变了引用，析构也可以改变引用 this.permissionList.push({...this.addForm})
    5. 组件参数校验 props使用对象键值对进行检查，多个时 值/value 使用数组，更多的校验要求时value使用对象属性 

### 在cube的项目中遇到的关于项目的问题
    1.打包命令配置 package.json中进行命令配置。config文件目录中存放不同环境对应的接口地址或资源地址，build中存放webpack配置文件，webpack配置文件中配置具体项
    2.接口获取权限列表，根据addroute进行动态添加路由，permission.js筛选和追加页面权限
    3.组件化其实可以看作是构造函数，组件中只写数据处理逻辑及返回值，由父组件传值给子组件进行处理
    4.使用element进度条组件时，使用http-request时on-porgress无法触发，使用http-request去做进度条，将每一个上传时组件数据增加一个字段，成功时移除该字段
    5.element中监听键盘事件需要加native





    