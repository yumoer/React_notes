# 1. 说说你对redux的理解
* redux是一个独立专门用于做状态管理的Js库而并非react插件库，他可以用在react，angular，vue项目中，但基本配合react使用
* 作用：集中式管理react应用的多个组件共享的状态
* 核心API
	* 创建包含指定reducer的store对象
	* import {createStore} from 'redux'
	* import counter from './reducers/counter'
	* const store = createStore(counter)
	* store对象的方法
	* store.getState() //获得状态
	* store.dispatch({type:'INCREMENT', number}) //更新状态
	* store.subscribe(render) //订阅状态

# 2. 说说react-redux库
* 是一个react插件库，专门来简化react中的redux
* react-redux将所有组件分成两大类
	* UI组件
		* 不使用任何Redux的ApI
		* 一般保存在components文件夹下
		* 只负责UI的呈现，不带任何业务逻辑
		* 通过props接收数据（一般函数和数据）
	* 容器组件
		* 使用Redux的API
		* 一般保存在containers文件夹下
		* 负责数据管理和业务逻辑，不负责UI的呈现
		
# 3. 说说如何实现异步redux
* 引入redux-thunk（异步中间件）index.js
	* import {createStore, applyMiddleware} from 'redux'
	* import thunk from 'redux-thunk
* 在store中应用异步中间件 index.js
	* const store = createStore(
  	* counter,
  	* applyMiddleware(thunk) // 应用上异步中间件
	* )
* 在异步代码中发布一条同步更新 actions.js
	* // 异步action creator(返回一个函数)
	* export const incrementAsync = number => {
	* return dispatch => {
    * setTimeout(() => {
    *  dispatch(increment(number))
    * }, 1000)
    * }
	* }
* 定义 components组件 counter.jsx
	* incrementAsync = () => {
	* const number = this.refs.numSelect.value*1
	* this.props.incrementAsync(number)
	* }

* 包装组件containers app.jsx 
	* import {increment, decrement, incrementAsync} from '../redux/actions' // 向外暴露连接App组件的包装组件
	* export default connect(
	* state => ({count: state}),
	* {increment, decrement, incrementAsync}
	* )(Counter)

# 4. 说说你对纯函数与高阶函数的理解
* 纯函数
	* 只要是同样的输入，必定得到同样的输出
		* 不得修改参数
		* 不能调用系统的I/O的api
		* 不能调用Date.now()或者Math.random()等不纯的方法
	* reducer函数必须是一个纯函数
* 高阶函数
	* 参数是函数、返回值为函数
	* 常见高阶函数：
		* 定时器设置函数
		* 数组的map/filter/reduce/find...
		* react-redux中的connect函数
	* 功能：实现更加动态，可扩展的功能

# 5. redux结构图
![](https://i.imgur.com/nk2hvVJ.png)
