# MpVue框架的学习
> 慢慢学习mpvue

## 环境准备
    1.安装node
    2.安装vue-cli脚手架  npm install vue-cli -g
    3.创建项目  vue init mpvue/mpvue-quickstart mpvue
    4.准备Appid
>[点击查看MpVue项目demo](https://github.com/LemonYF/mpvue)

## 目录结构
#### 1.package.json文件

package.json是项目的主配置文件，里面包含了mpvue项目的基本描述信息、
项目所依赖的各种第三方库以及版本信息、以及可执行的脚本信息
我们看到该文件中的scripts部分配置了4个可执行的命令：
```javascript
"dev": "node build/dev-server.js",
"start": "node build/dev-server.js",
"build": "node build/build.js",
"lint": "eslint --ext .js,.vue src"
```
#### 2.project.config.json文件

project.config.json文件是用于管理微信开发者工具的小程序项目的配置文件，
其中记录了小程序的appid、代码主目录、以及编译选项等等信息，
在微信开发者工具中导入小程序项目的时候主要是通过该配置文件读取和写入配置信息。

#### 3.static目录
static目录可以用于存放各种小程序本地静态资源，如图片、文本文件等。
代码中可通过相对路径或绝对路径进行访问， 如：
```javascript
<img src="/static/button.png" />
<img src="../../../static/button.png" />
```
#### 4.config目录
config目录下包含了用于开发和生产环境下的不同配置，
dev.env.js用于开发环境，prod.env.js用于生产环境，
你可以将开发阶段和生产阶段不一样的信息（如后台API的url地址等）配置到这两个文件中去，
然后在代码中以变量的形式进行引用。例如，这2个文件中分别配置了不同的API_BASE_URL值：

```javascript
// dev.env.js
module.exports = merge(prodEnv, {
  NODE_ENV: '"development"',
  API_BASE_URL: '"http://127.0.0.1:8080/api"'
})

// prod.env.js
module.exports = {
  NODE_ENV: '"production"',
  API_BASE_URL: '"https://www.my-domain.com/api"'
}
```

那你在编写请求后端API的代码时，你就可以使用这个环境配置，像这样：
```javascript
const baseURL = process.env.API_BASE_URL
wx.request({
  url: `${baseURL}/products`
})
```
#### 5.src目录
src目录是我们主要进行小程序功能编写的地方。默认生成的demo代码为我们创建了几个子目录：components、pages和utils，还有2个文件：App.vue和main.js。其实它们都不是必须的，可以按照自己的风格进行定义和配置。不过默认创建的这个结构基本上是一个约定俗成的结构了，比较易于理解，所以我们可以遵循这个结构进行开发。

* components：在实际开发中，我们可以尽量将界面上可复用的部分，提取成vue组件放入该目录
* pages：存放小程序的页面。请遵循每个小程序页面放入一个单独子目录的组织形式
* utils：可选（可删）。可以将代码中一些公用工具函数组织成模块放入该目录下
可新建其他目录，存放你希望组织起来的代码。比如公用的业务逻辑代码、请求后台API的代码等等
* main.js + App.vue：这两个是入口文件，相当于原生小程序框架中的app.json和app.js的复合体。

