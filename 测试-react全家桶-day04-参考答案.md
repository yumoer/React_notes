# 1. 说说你对redux的理解
	1). redux是一个独立专门用于做状态管理的JS库(不是react插件库)
	2). 可以与任何前端库配合使用, 但最合适的是与react库配合
	3). 作用: 集中式管理react应用中多个组件共享的状态
	4). 提供的API:
		createStore()
		applyMiddleWare()
		combineReducers()
		store.getState()/dispatch()/subscribe()
	
# 2. 说说react-redux库
	1). 一个react插件
	2). 专门用来简化react应用中使用redux
	3). 2种组件:
		UI组件: 没有使用任何redux语法的组件, 接收容器组件传入的一般/函数属性
		容器组件: 通过connect函数产生的组件, 与redux进行通信(读取状态/更新状态)
	4). 提供的API:
		Provider组件: 接收store属性, 并将其共享给所有的容器组件
		connect函数: 包装UI组件, 产生容器组件

# 3. 说说如何实现异步redux
	1). redux本身是不能执行异步处理的
	2). 下载redux异步中间件插件: redux-thunk
	3). 在createStore()时, 指定使用thunk中间件
	4). 在actions中, 定义返回函数的异步action, 在函数中执行异步代码最终dispatch同步action

# 4. 说说你对纯函数与高阶函数的理解
	1). 纯函数: 一类特别的函数
		多次调用, 如果实相同, 返回值也必须相同
		不能修改参数
		不能调用不纯的函数
		不同进行文件流操作
	2). 高阶函数: 一类特别的函数
		参数是函数或者返回值是函数
		常见: 定时器设置函数/数组的遍历相关的方法/connect()
		作用: 使用函数功能更动态,更可扩展
		
# 5. redux结构图


