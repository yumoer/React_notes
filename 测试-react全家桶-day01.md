# 1. 说说React的特点和高效的原因
	特点：
	* 声明式编程
	* 组件化编程
	* 前台渲染、后台渲染、ReactNative
	* 高效
	* 单向数据流	 
	高效：
	*虚拟Dom 减少界面更新的次数，不总是直接操作Dom
	*Dom Diff算法，最小化页面重绘次数

# 2. 使用2种方式定义一个简单组件
	* 工厂函数组件
		* function test(){
		* return <h1>工厂函数组件</h1>
		* }
	* ES6类组件
		* class test extends React.Component{
		*  render(){
		*   return <h1>ES6类组件</h1>
		*  }
		* } 
	* ReactDOM.render(<test/>, document.getElementById('example1'))
	
# 3. 说说组件对象的3大属性
	* state
		* 是组件对象最重要的属性，值是对象（可以包含多个数据）
		* 被称为“状态机”，通过更新组件的state来更新对应的页面显示（重新渲染组件）
			初始化 this.state = { name:val }
			读取   this.state.name
			更新状态 this.setState({name:val})
	* props
		* 每个组件都会有props属性
		* 组件标签的所有属性都保存在props中
			作用：通过标签属性从组件外向组件内传递变化的数据
			注意：组件内部不要修改props数据
		* 内部读取某个属性
			this.props.propertyName
		* 对props中的属性值进类型限制和必要性限制
			类组件.propTypes = {
				neme：PropType.string.isRequired //必填项
				age：PropType.string 	
			}
		* 默认属性值
			类组件.defaultProps = {
				name：'Jason'
			}
		* 扩展属性：将对象的所有属性通过props传递
			<Person {...person}/>
		* 组件类的构造函数
			constructor(props){
				super(props)
				console.log(props) //查看所有属性
			}
	* refs
		组件内的标签都可以定义ref属性来标识自己
		<input type="text" ref={input => this.msgInput = input}/>
		在组件内部可以通过this.msgInput来得到对应真实的Dom元素
		作用：通过ref获取组件内容特定标签对象，进行读取其相关数据
	* 区别props和state
		state：组件自身内部可变化的数据
		props：从组件外部向组件内部传递数据，组件内部只读取不修改
			
# 4. React组件化编码的基本流程	
	1. 拆分组件：拆分界面抽取组件
	2. 实现静态组件：使用组件实现静态页面效果
	3. 实现动态组件
		1. 设计初始化数据，指定初始化数据，并显示
		2. 交互：给特定标签绑定特定事件监听（状态在哪个组件，更新状态的行为（函数）就应该定义在哪个组件）

# 5. 说说你对2种类型容器的理解
	数组：数组中存储的数据都是有序的，通过下标取值
	对象：对象中存储的数据都是以键值对存在的，通过obj.键取值
