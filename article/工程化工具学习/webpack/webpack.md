安装webpack
1. npm init 初始化package.json
2. 安装webpack和webpack-cli
3. webpack配置项 创建webpack.config.js(默认，可修改)文件来配置webpack
4. 具体插件配置查看文档
```javascript
// 基于node
module.exports = {
    entry: '',               // 入口文件
    output: {},              // 出口文件
    module: {                // 处理对应模块
        rules: []
    },              
    plugins: [],             // 对应的插件
    devServer: {},           // 开发服务器配置
    mode: 'development'      // 模式配置
}
```