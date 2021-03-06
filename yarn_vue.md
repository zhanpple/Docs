# phenix

> A Vue.js project

[TOC]

```
██╗    ██╗ █████╗ ███╗   ██╗
██║    ██║██╔══██╗████╗  ██║
██║ █╗ ██║███████║██╔██╗ ██║
██║███╗██║██╔══██║██║╚██╗██║
╚███╔███╔╝██║  ██║██║ ╚████║
 ╚══╝╚══╝ ╚═╝  ╚═╝╚═╝  ╚═══╝
                            
```

## 一、Build Setup
预先安装Node.js(附带npm)

``` bash
# install yarn
npm install -g yarn

# 查看版本
node -v

# serve with hot reload at localhost:8080
npm run dev

# 全局安装vue脚手架 npm install -g vue-cli 需要翻墙
npm install -g vue-cli 

# 如果之前已经安装过旧版本（非3.x）脚手架，需要卸载旧版本：
npm uninstall vue-cli -g
# 安装脚手架，用于生成项目
npm install -g @vue/cli
#yarn 安装
yarn global add @vue/cli
yarn global add @vue/cli-init
#快速原型开发，编译.vue文件
npm install -g @vue/cli-service-global


#  创建一个基于 webpack 模板的新项目
 vue init webpack phenix
 ...
 cd phenix
 yarn
 yarn start
 
#vue-cli3
vue create my-project
 
 
 
```

### 1.1[使用 vue-cli 3 快速创建 Vue 项目](使用 vue-cli 3 快速创建 Vue 项目.md)

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

### 1.2目录结构

* node_modules 			依赖的模块
* public                             静态资源模块
  * index.html			 入口的html文件
  * favicon.ico             浏览器title部分icon文件
* src                                  开发的目录
  * assets                    所有静态资源（会被webpack处理的）
  * components        所有组件
  * views                    路由页面
  * App.vue               应用程序组件（vue cli中组件文件首字母大写）
  * main.js                 项目入口文件
  * router.js               路由文件
  * store.js                 store文件
* .broserslistrc              浏览器配置
* .eslintrc.js                  js校验配置
* .gitnore                      git提交时忽略的配置文件
* babel.config.js         babel配置文件
* package.json            模块配置文件
* postcss.config.js       css配置文件

webpack配置

 	vue cli 也是通过webpack配置的，因此我们可以定义webpack配置

在vue.config.js文件中（我们可以自定义）

​	通过configureWebpack定义webpack配置

webpack拓展

​	在加载机中（module加载规则），

include   加载机处理的目录

exclude  加载机不能处理的目录

我们可以通过vue config 将所有配置输出（包括webpack）

## 二、引入Element UI

```$xslt
npm i element-ui -S
H:\Yarn-Manage\phenix>npm i element-ui -S
npm WARN deprecated mixin-deep@1.3.1: Critical bug fixed in v2.0.1, please upgrade to the latest version.
npm WARN deprecated set-value@2.0.0: Critical bug fixed in v3.0.1, please upgrade to the latest version.
npm WARN deprecated set-value@0.4.3: Critical bug fixed in v3.0.1, please upgrade to the latest version.
npm WARN deprecated browserslist@2.11.3: Browserslist 2 could fail on reading Browserslist >3.0 config used in other tools.
npm WARN deprecated browserslist@1.7.7: Browserslist 2 could fail on reading Browserslist >3.0 config used in other tools.
npm WARN deprecated flatten@1.0.2: I wrote this module a very long time ago; you should use something else.
npm WARN deprecated bfj-node4@5.3.1: Switch to the `bfj` package for fixes and new features!
npm WARN rm not removing H:\Yarn-Manage\phenix\node_modules\.bin\browserslist.cmd as it wasn't installed by H:\Yarn-Manage\phenix\node_modules\browserslist
npm WARN rm not removing H:\Yarn-Manage\phenix\node_modules\.bin\browserslist as it wasn't installed by H:\Yarn-Manage\phenix\node_modules\browserslist

> core-js@2.6.9 postinstall H:\Yarn-Manage\phenix\node_modules\core-js
> node scripts/postinstall || echo "ignore"

Thank you for using core-js ( https://github.com/zloirock/core-js ) for polyfilling JavaScript standard library!

The project needs your help! Please consider supporting of core-js on Open Collective or Patreon: 
> https://opencollective.com/core-js 
> https://www.patreon.com/zloirock 

Also, the author of core-js ( https://github.com/zloirock ) is looking for a good job -)


> uglifyjs-webpack-plugin@0.4.6 postinstall H:\Yarn-Manage\phenix\node_modules\webpack\node_modules\uglifyjs-webpack-plugin
> node lib/post_install.js

npm notice created a lockfile as package-lock.json. You should commit this file.
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@1.2.9 (node_modules\fsevents):
npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@1.2.9: wanted {"os":"darwin","arch":"any"} (current: {"os":"win32","arch":"
x64"})

+ element-ui@2.9.2
added 81 packages from 65 contributors, removed 45 packages, updated 823 packages and audited 11562 packages in 478.78s
found 6 vulnerabilities (4 moderate, 2 high)
  run `npm audit fix` to fix them, or `npm audit` for details

```

## 三、[引入IView](https://www.iviewui.com)

```
yarn add iview
```
## 四、Vue.js Ajax(axios)

 Vue.js 2.0 版本推荐使用 axios 来完成 ajax 请求。

 Axios 是一个基于 Promise 的 HTTP 库，可以用在浏览器和 node.js 中。

 Github开源地址： https://github.com/axios/axios

```
yarn add axios
yarn add vue-axios
```
进行安装。
安装完成后在main.js中使用axios，在main.js中加入以下代码
```
import axios from 'axios'
import VueAxios from 'vue-axios'
Vue.use(VueAxios, axios)
```

这样就可以在全局中使用axios做请求了。
我们在表单校验通过的时候使用axios来请求后台。代码如下

```vue
handleSubmit(name) {
                this.$refs[name].validate((valid) => {
                    if (valid) {
                        this.axios({
                            url: '',//请求的地址
                            method: 'post',//请求的方式
                            data: this.formInline//请求的表单数据
                        }).then(res => {
                            console.info('后台返回的数据', res.data);
                        }).catch(err => {
                            console.info('报错的信息', err.response.message);
                        });
                    } else {
                        this.$Message.error('表单校验失败!');
                    }
                })
            }
```



## 五、数据定义

通常来说，网站中有两类数据

- 不变的数据， 每次打开浏览器看到的结果都是一样，因此这类数据我们可以直接写在页面中，作为同步数据，当我加载完数据，我们可以直接使用这类数据
- 可变的数据， 每次打开浏览器看到的结果都是不一样， 因此这类数据我们可以作为异步数据，通过异步请求获取，当我们的页面加载完成之后，通过异步请求

## 六、开发模块顺序

1. 获取数据并存储
2. 分析页面结构，写视图
3. 根据视图写样式
4. 绑定交互

## 七、技巧

1. ### 路由守卫

   vue路由提供了三种监听路由变化的方式

   A 第一种 全局监听

   a. 在路由实例化对象上，通过beforeEach, afterEach 等方法监听路由改变

   参数是回调函数 参数1.表示当前路由对象  参数2 表示上一个路由对象

   ​		如果是beforeEach，会出现第三个参数，类似express路由中间件的第三个参数，next方法，是否继续执行，该方法必须执行（next()）。

   B 第二种 局部监听

    只针对某个组件监听路由变化

   组件实例化对象上，通过beforeRouteEnter, beforeRouteLeave, beforeRouteUpdate等方法

   beforeRouteEnter（a,b,c）

   参数a：表示当前路由对象

   参数b：表示上一个路由对象

   参数c：表示next，必须执行

   C 第三种 watch监听

   ​	 通过组件实例化对象watch监听路由数据的变化

   ​    通过监听$route属性的变化来监听路由

   ​	

   ```
   //监听路由数据的变化
   //newVal： 表示当前路由   oldVal： 表示上一个路由
           watch: {
               $route(newVal, oldVal) {
                   console.log('Root Route: ' ,this.$route)
               }
           }
   ```

   【注意】watch需要放在生命周期长的父组件中才能生效

   全局监听也称之为全局路由守卫

   局部监听也称之为局部路由守卫

   


## 附件：

### 1.npm 和yarn比较

|                 npm                  |             yarn              |             用法             |
| :----------------------------------: | :---------------------------: | :--------------------------: |
|             npm install              |         yarn install          | 一键安装package.json的所有包 |
|  npm install [package] --save / -S   |      yarn add [package]       |      安装到dependencies      |
| npm install [package] --save-dev/ -D | yarn add [package] --save-dev |    安装到devDependencies     |
|       npm i [package]@[版本号]       |  yarn add [package]@[版本号]  |      指定版本号下载更新      |
|    npm install [package] --global    |   yarn global add [package]   |        全局安装某个包        |
|         npm update --global          |      yarn updade upgrade      |          更新所有包          |
|       npm uninstall [package]        |     yarn remove [package]     |          删除某个包          |

![npm 和yarn比较](RES/3029162-b71cccb4632a07ad.webp)


### 2.Vue 调用子组件方法
```vue
this.$refs.fb.setText(txt)
this.$refs[name].setText(txt)

```



### 3.缺少windows构建插件**



**解决方法：在命令行工具中运行：npm install –global –production windows-build-tools （全局安装windows构建工具）**