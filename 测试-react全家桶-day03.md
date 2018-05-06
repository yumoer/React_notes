# 1. 说说如何在react应用中发送ajax请求
* jQuery：太重不建议使用
* axios：
	* 轻量级
	* 封装xmlHttpRequest对象的ajax
	* pormise风格
* fetch：原生函数，不支持老版本浏览器

# 2. 说说你对路由的理解
* 路由是一种key：value的映射关系
* key:路径 value：function/component
* 后台路由：node服务器路由，val是func,用来处理客户端提交的请求并返回响应数据
* 前台路由：浏览器端路由，val为component,当请求的路由为path时，并没有发送请求而是更新显示对应的组件

# 3. 说说你对请求参数的理解
* query参数
	* 路由的path：/xxx
	* 请求路径： /xxx?name=xx&age=xx
	* ?后面的就是query参数（查询字符串）
* param参数
	* 路由的path: /xxx/:name/:age
	* 请求路径: /xxx/jack/18
	* param参数：name=jack,age=18
	* params.name, params.age
	
# 4. 说说你对事件的理解
* 原生Dom事件
	* 绑定事件
		* 事件名：有限的几个不能随便写
		* 回调函数：接收数据，处理事件
	* 触发事件
		* 用户操作界面、事件名、数据
* 自定义事件（消息机制）
	* 绑定事件监听
		* 事件名:任意
		* 回调函数：通过形参接收数据，回调函数处理事件
	* 触发事件（编码）
		* 事件名：与绑定的事件监听事件名一致
		* 数据会自动传递给回调函数
		
# 5. 比较2种react中组件间通信方式
* props
	* 共同的数据放在父组件上，特有的数据放在自己组件内部（state）
	* 兄弟组件间的通信需要通过更改父组件的状态才能完成
	* props可以传递一般数据和函数数据，并且只能逐层传递
	* 一般数据 -> 父组件传递给子组件 -> 子组件读取数据
	* 函数数据 -> 字组件传递给fu组件 -> 子组件调用函数
* 消息订阅（subscribe）和发布(publish)
	* 需要引入第三方插件库（PubSubJS）
	* 兄弟组件间的通信不在依靠于父组件，而是通过sub和pub的方式来传递数据
* redux

