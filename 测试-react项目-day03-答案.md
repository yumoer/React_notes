## 1. 说说react-router-dom库(作用和API)
	1）作用：用来实现SPA
	2) 组件：HashRouter/BrowserRouter/Route/Switch/Redirect/LInk?navLink
	   对象：所有路由组件的props有几个属性：
			history（路由管理的对象）：push（）、replace（）、goBack（）、goForward（）

## 2. 说说redux库(作用和API)

## 3. 说说react-redux库(作用和API)
	1). 作用: 简化在组件中使用redux的编码
	2). 提供2个API
		<Provider store={store}>: 为所有容器组件提供全局的store对象
		connect()(UI组件): 包装ui组件生成容器组件, 实现ui组件与redux的数据通信 

## 4. 编写一个同步action和异步action
	const receiveUser = (user) => ({type: RECEIVE_USER, data: user})
	const getUser = () => {
		return async dispatch => {
			const response = await reqUser()
			const result = response.data
			if(result.code===0) {
				dispatch(receiveUser(result.data))
			}
		}
	}

## 5. chrome调试应用的常用功能(窗口)
	Elements: 查看DOM标签和样式
	Console: 查看打印和错误信息
	NetWork: 查看请求(url, 请求方式, 请求参数)和响应
	Application: 查看浏览器端存储(localStorage, cookie)
	Sources: debugger调试

	react: 查看react组件(state, props)
	redux: 查看redux管理的state
 

