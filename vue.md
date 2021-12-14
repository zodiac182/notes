# 什么是node.js
Node.js 是一个基于 Chrome V8 引擎的 JavaScript 运行环境。Node.js 使用了一个事件驱动、非阻塞式 I/O 的模型，使其轻量又高效。  

Node 是一个让 JavaScript 运行在服务端的开发平台。Node是一个基于Chrome JavaScript运行时建立的平台， 用于方便地搭建响应速度快、易于扩展的网络应用。Node 使用事件驱动， 非阻塞I/O 模型而得以轻量和高效，非常适合在分布式设备上运行数据密集型的实时应用。 
node.js不是一门语言，不是库，不是框架，只是一个javeScript运行时环境。简单的就是node.js可以解析和执行javeScript代码，以前只有浏览器可以解析执行JaveScript代码，现在的javeScript可以完全脱离浏览器来运行   

### npm包管理工具
使用node开发还可以使用node自有配套的npm包管理工具，NPM是随同NodeJS一起安装的包管理工具，能解决NodeJS代码部署上的很多问题，常见的使用场景有以下几种：
* 允许用户从NPM服务器下载别人编写的第三方包到本地使用。
* 允许用户从NPM服务器下载并安装别人编写的命令行程序到本地使用。
* 允许用户将自己编写的包或命令行程序上传到NPM服务器供别人使用。
* npm(包管理工具)是基于Node.js的前端项目包管理工具，是项目中对各种程序包的依赖管理，传统的开发项目主要是后端，现在技术在更新，前端有了框架的开发模式管理，也需要用包管理工具的思想去管理，目的是简化第三方程序包在项目中引用复杂化。前端的JS包是全世界JavaScript天才开发共享的各种代码模块，把这些代码模块都按照一个独立的软件功能统一在一个库中，一个代码模块是一个程序包（package，即代码模块）。它是世界上最大的软件注册表。
	* 官网：　https://www.npmjs.cn/  


* nodejs是一个服务js平台，有自身带的npm（基于 Node.js的前端项目包管理工具），有第三方的grunt（基于Node.js的前端项目构建工具即即脚手架）、有第三方的express（路由功能）等强大的代码与项目管理应用。还有自身带的webpack（基于 Node.js的前端项目部署打包工具），v8（谷歌客户端浏览器javascript引擎）等强大的功能。  
*grunt是基于Node.js的前端Javascript语言项目构建工具，即脚手架。一句话：构建项目自动化。对于需要反复重复的任务，例如压缩（minification）、编译、单元测试、linting等，自动化工具可以减轻你的劳动，简化你的工作。当你在 Gruntfile 文件正确配置好了任务，任务运行器就会自动帮你或你的小组完成大部分无聊的工作。  
官网：https://www.gruntjs.net/  


***

# vue.js
## 1. 基础
Vue是渐进式JavaScript 框架，它用在前端和html和js打交道，主要特点是易用，灵活，高效，实现html端对数据展示的控制。 
* Vue CLI 
Vue CLI 是一个基于 Vue.js 进行快速开发的完整系统，它算是个快速开发工具，通过简单的命令行就可以搭建出一个vue结构的项目，并做了一些默认配置。常和VS Code一起使用，用于管理前端项目。
* Vuex
Vuex就是本地的一个store（仓库），可以理解成容器，和其它的容器不同之处是Vuex 的状态存储是响应式的，可以认为它是专门为Vue开发的，主要是解决vue绑定本地储存数据问题。比如我后台登录账号，数据表单等，有了本地容器再做单页应用程序将是一种不同的体验。

* Vue Router
Vue Router 是 Vue.js 的官方路由。它与 Vue.js 核心深度集成，让用 Vue.js 构建单页应用变得轻而易举。这个也是针对单页应用而出的。注意这个Vue Router是运行在服务端的，也就是和nodeJs发生关系。

## 2. 用法
### 2.1 安装
	cnpm install vue@next
### 初始化一个项目
#### * 命令行工具vue cli
vue cli用于快速搭建大型单页应用  

	# 安装vue cli
	$ cnpm install -g @vue/cli
	# 安装 @vue/cli-int：
	$ cnpm i -g @vue/cli-init
	# 创建vue 项目
	$ vue init webpack vue-study

#### * Vite
Vite 是一个 web 开发构建工具，由于其原生 ES 模块导入方式，可以实现闪电般的冷服务器启动。  

	# 构建项目
	$ npm init @vitejs/app <project-name> -- --template vue
	$ cd <project-name>
	$ npm install
	$ npm run dev

#### expose port
	# 当运行npm run dev | serve 命令时，会显示一下内容.  
	# 此时不能通过公网IP进行访问
	  vite v2.7.1 dev server running at:

	  > Local: http://localhost:3000/
	  > Network: use `--host` to expose
##### 解决方法：
* 1. 修改vite.config.js：  
	import vue from '@vitejs/plugin-vue'
	/**
	 * https://vitejs.dev/config/
	 * @type {import('vite').UserConfig}
	 */
	export default {
	  plugins: [vue()],
	  server: {				// ← ← ← ← ← ←
		host: '0.0.0.0'	// ← 新增内容 ←
	  }						// ← ← ← ← ← ←
	}
* 2. 通过 Vite CLI 配置  
	执行命令： npx vite --host 0.0.0.0
* 3. 修改npm脚本
	# 修改 package.json 文件中 scripts 节点下的脚本，如下：  
	"scripts": {
	  "dev": "vite --host 0.0.0.0",
	  "build": "vite build",
	  "serve": "vite preview --host 0.0.0.0"
	}

	
