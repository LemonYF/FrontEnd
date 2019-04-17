安装webpack
1. npm init 初始化package.json
2. 安装webpack和webpack-cli
3. webpack配置项 创建webpack.config.js(默认，可修改)文件来配置webpack
4. 具体插件配置查看文档
>es6Js文件热更新使用babel
CSS文件使用
```javascript
// 基于node
var htmlWebpackPlugin = require('html-webpack-plugin')

module.exports = {
    entry: '',               // 入口文件
    output: {},              // 出口文件
    module: {                // 处理对应模块
        rules: [
                    {
                        test: /\.js$/,
                        exclude: /node_modules/,
                        loader: 'babel-loader'
                    }
                ]
    },              
    plugins: [               // 对应的插件
        // html 生成插件
        new htmlWebpackPlugin()
    ],             
    devServer: {},           // 开发服务器配置
    mode: 'development'      // 模式配置
}
```

5. 热更新需要配置本地服务器webpack-dev-server及html-webpack-plugin
>webpack.config.js里配置， npm安装插件

```javascript

plugins: [               // 对应的插件
        // html 生成插件
        new htmlWebpackPlugin()
    ],
devServer: {    // 开发服务器配置
        contentBase: path.join(__dirname, "dist")
    }
```

6. npm简化启动命令
在package.json中设置script的命令
```javascript
"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "dev": "webpack-dev-server --open"
  }
```
