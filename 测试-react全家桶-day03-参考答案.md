# 1. 说说如何在react应用中发送ajax请求
	1). 使用谁发请求?
		react库本身不可以
		axios: 封装的XMLHTTPRequest, promise风格, 浏览器端和node服务器端
		fetch: 较新的浏览器提供的新的ajax请求方式, 可以引入fetch.js来实现兼容处理
	2). 在哪执行?
		初始显示: componentDidMount()
		交互: 事件回调函数/componentWillReceiveProps()

# 2. 说说你对路由的理解
	1)什么是路由?
		a.一个路由就是一个映射关系(key:value)
		b.key为路由路径, value可能是function/component
	2)路由分类
		a.后台路由: node服务器端路由, value是function, 用来处理客户端提交的请求并返回一个响应数据
		b.前台路由: 浏览器端路由, value是component, 当请求的是路由path时, 浏览器端前没有发送http请求, 但界面会更新显示对应的组件 

# 3. 说说你对请求参数的理解
	1). query参数
		路由的path: /xxx
		请求的路径: /xxx?name=tom&age=18
		?后面的部分就是query参数: name=tom, age=18
	2). param参数
		路由的path: /xxx/:name/:age
		请求的路径: /xxx/jack/18
		param参数: name=jack, age=18
		params.name, params.age
# 4. 说说你对事件的理解
	1). 绑定事件监听
		事件名
		事件回调函数: 接收数据并处理
	2). 触发事件
		事件名
		数据

# 5. 比较2种react中组件间通信方式
	1). 方式一: 通过props传递
		通过props可以传递一般数据和函数数据, 只能一层一层传递
		一般数据-->向子组件
		函数数据-->子组件向父组件通信
	2). 方式二: 使用消息订阅(subscribe)-发布(publish)机制
		实现库: PubSubJS
		组件A: 发布消息
		组件B: 订阅消息, 接收消息, 处理消息
		优点: 对组件关系没有限制

