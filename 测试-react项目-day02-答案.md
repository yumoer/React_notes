## 1. 写出6个常用webstorm命令
	向下复制一行(Duplicate Lines)                          Ctrl+Down
	修改变量名与方法名	                                    Alt+Shift+R
	向下移动行	                                            Alt+Down
	单选注释                                               Ctrl + /
	多行注释                                               Ctrl+Shift+/
	格式化代码	                                            Ctrl+shift+F
	大小写转换                                             Ctrl+shift+X
	查找/替换(当前)                                        Ctrl+F
	删除一行或选中行	                                    Ctrl+D
	查找文件	                                            Double Shift	
	查找/替换(全局)                                        Ctrl+H

## 2. 后台路由回调函数处理的3步
	1). 通过req读取请求参数数据
	2). 处理数据(与数据库交互)
	3). 通过res向浏览器端返回响应

## 3. 使用mongoose操作数据库的基本编码流程
	1). 连接数据库
    2). 定义schema和Model
    3). 通过Model函数对象或Model的实例的方法对集合数据进行CRUD操作 
	
## 4. 写出一个简单的package.json(5个部分)
	{
		"name": "gboss",
		"version": "1.0.0",
		"scripts": {
			
		},
		dependencies: {},
		devDependencies: {}
	}
## 5. async与await的理解和使用
	1). 理解: 同步编码方式实现异步ajax请求, 简化promise的使用
	2). 使用:
		在调用接口请求函数语句的左侧指定await, 直接接收异步返回的response
		在await所在的函数左侧指定async

