# React

## 概念
React 是一个用于构建用户界面的库。  
***
## React 特点
* 声明式设计 −React采用声明范式，可以轻松描述应用。

* 高效 −React通过对DOM的模拟，最大限度地减少与DOM的交互。
	* DOM：文档对象模型（Document Object Model）

* 灵活 −React可以与已知的库或框架很好地配合。

* JSX − JSX 是 JavaScript 语法的扩展。React 开发不一定使用 JSX ，但建议使用它。

* 组件 − 通过 React 构建组件，使得代码更加容易得到复用，能够很好的应用在大项目的开发中。

* 单向响应的数据流 − React 实现了单向响应的数据流，从而减少了重复代码，这也是它为什么比传统数据绑定更简单。
***
## 使用
### 安装
1. 安装nodejs
2. 安装create-react-app,构建react开发环境  
	```
	npm install -g create-react-app
	create-react-app my-app
	cd my-app/
	npm start
	```
3. 目录结构  
	```
	my-app/
	  README.md
	  node_modules/
	  package.json
	  .gitignore
	  public/
		favicon.ico
		index.html
		manifest.json
	  src/
		App.css
		App.js
		App.test.js
		index.css
		index.js
		logo.svg
	```
### HTML模板
* index.html网页源码
	```
	<!DOCTYPE html>
	<html>
	  <head>
		<script src="../build/react.js"></script>
		<script src="../build/react-dom.js"></script>
		<script src="../build/browser.min.js"></script>
	  </head>
	  <body>
		<div id="example"></div>
		<script type="text/babel">
		  // ** Our code goes here! **
		</script>
	  </body>
	</html>
	```
	* <script> 标签的 type 属性为 text/babel。
	* React独有的JSX语法，跟JavaScript不兼容。凡是使用JSX的地方，都要加上type="text/babel"
	* JSX 语法  
	HTML语言直接写在JavaScript语言之中，不加任何引号，这就是JSX的语法，它允许HTML与JavaScript的混写  
	遇到 HTML 标签（以 < 开头），就用 HTML 规则解析；遇到代码块（以 { 开头），就用 JavaScript 规则解析  
	```
	var names = ['Alice', 'Emily', 'Kate'];
	ReactDOM.render(
	  <div>
	  {
		names.map(function (name) {
		  return <div>Hello, {name}!</div>
		})
	  }
	  </div>,
	  document.getElementById('example')
	);
	```
	
* ReactDOM.render()
ReactDOM.render 是 React 的最基本方法，用于将模板转为 HTML 语言，并插入指定的 DOM 节点。
	```
	ReactDOM.render(
	  <h1>Hello, world!</h1>,
	  document.getElementById('example')
	);
	```