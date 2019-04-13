#VUE  

v-bind 特性被称为指令 缩写可以去掉V-bind 用:来替代
v-on  监听事件  缩写可以用@来代替
v-for 指令可以绑定数组的数据来渲染一个项目列表
v-if  可设置TRUE和false来设置内容的显示还是隐藏
v-on 指令添加一个事件监听器（如点击事件）
v-model 指令，它能轻松实现表单输入和应用状态之间的双向绑定
在 Vue 里，一个组件本质上是一个拥有预定义选项的一个 Vue 实例
created   在实例创建完成后被立即调用
<span v-once>这个将不会改变: {{ msg }}</span>
为了输出真正的 HTML，你需要使用 v-html 指令
，Vue.js 都提供了完全的 JavaScript 表达式支持  限制就是，每个绑定都只能包含单个表达式
watch  
用 key 管理可复用的元素  比如两个文本框前后数据一致 如果想要不同  可设置key值
v-if 有更高的切换开销，而 v-show 有更高的初始渲染开销。因此，如果需要非常频繁地切换，则使用 v-show 较好；如果在运行时条件很少改变，则使用 v-if 较好。
当它们处于同一节点，v-for 的优先级比 v-if 更高
也可直接设置成“content=value”
# 组件化：细分代码  
      代码：template  style scipt
	  双向数据流：js内存属性的变化影响页面的变化
	              页面的变化影响内存属性的变化   IE9以上
    v-指令一般当做变量俩使用，如果写死咸亨一个值就没有意义了
	v-text  只能在双标签中使用
	v-html  简析HTML代码  是元素的innerhtml  不能有表达式
	v-if    元素是否移除
	v-show  元素是否显示或隐藏
	V-model  是双向的数据绑定
	v-for   列表渲染（遍历集合）
	v-bind:value 给VALUE赋值 是单向的数据绑定（js内存改变影响页面）
	class结合v-bind使用  v-bind:属性名=“表达式” 最总表达式运算结束的结果赋值给属性名
	一个样式：三元表示
	多个样式：返回对象  key是样式   true flase  做值
	data是一个函数  返回一个对象
	v-on：click
	methods 绑定事件的方法 其实是一个对象
	v-on:事件=“表达式||函数名”
	需要使用this来
	template模板中vue变量可以直接使用  在js中使用要机上this
	
	v-for  可以操作数组（item、index）和操作对象(value、key、index)  如果想要列表与对象的index一致  需要在列表中绑定数组的index值 ：key
	       最好设置key 提高性能
		   
		   
    组件  谁用谁就是爸爸（父组件）   谁被用就是儿子（子组件）
	     
		  父和子  使用的是父  被用的是子
		  父需要声明子组件  映入子组件对象
		  引入 组件对象
		  必须声明：components 组件名
	全局组件  不需要和声明
	           在min.js中引入和声明Vue.component
			   未来搜友的组件合一通过组件名直接使用
	接受父组件的参数props[]  可以传递属性和值(常量和变量) v-bind:
	                      
	注意：如果页面中有用到VUE的变量  那么必须在js中声名  或则会报错
	
	
	
	watch    监视值发生变化时调用
    created  在实例创建完成后被立即调用
	
	
	
	查看文档
	选项和分类  options/类别  和实例相关（el rander）
	全局 通过vue点出来的
	实例 组件内的this和new VUE()
	options代表new vue的参数或者export default里面的属性
	
#	过滤器：组件内的过滤器和全局过滤器
	        options中的filters（一个对象）
			vue.filters()全局过滤器
			全局组件：范围大 如果出现重名时 权利小
			组件内    权利大  范围小
			
#	vue直接操作dom
	        在制定元素上添加ref="名称"
			获取地方用 this.$refs.名称
			如果ref放在原生dom元素上  获取的是原生dom对象
			this.$refs.名称.操作
			如果ref放在组件dom元素上  获取的是组件dom对象
			this.$refs.名称.$el.操作
#   生命周期			
	new的一瞬间执行生命周期函数		
	beforeCreate  第一个生命周期函数   data和methods和页面都没被初始化
	事件处理函数||生命钩子		
	组件创建后  数据已经初始化datahemethods  但是DOM还未生成   无法操作DOM   经常会发起ajax请求    created（）事件处理函数
  	
	beforemount：当模板编译完成会执行beforemount此时内存中的模板结构还未渲染到页面，此时用户看到的只是模板页面，没有数据
	
	数据装载后  各类数据已经就位 将数据渲染到DOM上  DOM已经生成 最后你一个生命周期函数   mounted（）组件离开了创建阶段进入运行阶段
	第三方插件必须初始化的时候在mounted中初始化
	
#	computed 计算属性
	它的性能是比较高的，只有当他依赖的属性发生变化时，它才会重新请求计算，
	否则使用上一次的缓存值。所以如果一个庞大的数据项目，需要有缓存的，
	就可以用这种方法。可以减少请求次数，达到优化                            
	
	
#	Vue.use  安装注册
			
	mint-ui  使用vue写的 在script使用必须引用(按需引用)  在templert中可以直接使用  前提是应用了全部组件
	
#   Router	
	vue-router 路由   锚点值改变调用函数 vue开头
	
	rounter-link标签
	   去哪里 1 <rounter-link to="/bejing"></rounter-link>
	          2 <rounter-link :to="{name:'beijing'}"></rounter-link> 更便于维护  只用修改路由配置中的parth
	    view-router   有两大对象被挂载带实例this中
		$route (只读具备信息的对象)$router(具备功能)
		查询字符串的方式：？
		              查询query（id:""） parth不用改
		              获取路由参数  this.$route.query.id
		parth的方式：//类似漏油
			          查询params（id:""） parth后面加上/:id   类似（mvc的路由）
		              获取路由参数  this.$route.params.id
	vue跳转页面：this.$router.push('路径')；
	             this.$router.push({
				 name:'路由配置的参数'
				 })
				  this.$router。go(-1)上一个浏览器
				  this.$router。go( 1)下一个浏览器
				  this.$router.push({
				  //查询字符串的方式/music?id=1&name=2
				 name:'路由配置的参数',
				 query:{id:1,name:2}||params:{id:1,name:2}
				 })
	路由的核心：监视锚点值得改变人后往进放数据
	            windows.addEventListener('hashchange',function(){
				判断location.hash的值来填充不同的内容
				})
	重定向和404
	进入后默认就是/
	{parth:'/',rediect:'首页'}
    {parth:'*',component:"地址"}
	
	
	多视图
	以前一个坑对应一个路由显示一个组件
	一次行为=一个坑+一个路由+一个组件
	一次行为=多个坑+一个路由+多个组件
	components  多实体  是一个对象
	            key 对应师徒的name属性
				value 显示的组件对象
	rounter-vue 可以有多个  默认default
	[{
	parth:"/",
	components:{
	
	}
	}]
#	嵌套路由
	
	vue-resource
	可以安装插件 推介axios
	options预检请求是浏览器发现跨域+application/json请求就会自动发起，就会自动
	有content-type头(如果不想设置content-type可以emulateJSON:true来过滤服务端的头部验证)
	import axios from 'axios'
	vue.prototype.$axios=axios  给对象的原型挂载一个属性
	主要依赖fromdata的数据接收格式
	全局默认设置：axios.defaults.baseURL="地址"可以设置默认前置地址
	
	
	 this.$nextTick(function(){
	 我们可以看到它会等dom结构更新完成后再去获取更新后的innerHTML值
	 })
	 
	 
	 Vue.set(target,key,value)普通的情况下对Vue实例里面的数据进行更改，数据改掉了，但是呈现在页面的视图并没有发生变化，所以借用该方法视图也会跟着刷新
	  Vue.set(app.arr,0,'北京天安门');
	  Vue.delete(target,key)用法和原理与set添加元素是一样的道理
	  
#   vue自定义指令
    Vue.directive(id,[definition])指令函数
	Vue.directive('my-directive', {
                  bind: function () {},bind: 只调用一次，指令第一次绑定到元素时调用，用这个钩子函数可以定义一个在绑定时执行一次的初始化动作。
                  inserted: function () {},inserted: 被绑定元素插入父节点时调用（父节点存在即可调用，不必存在于 document 中）。
                  update: function () {},bind:update: 被绑定元素所在的模板更新时调用，而不论绑定值是否变化。通过比较更新前后的绑定值，可以忽略不必要的模板更新
                  componentUpdated: function () {},被绑定元素所在模板完成一次更新周期时调用。
                  unbind: function () {}unbind: 只调用一次， 指令与元素解绑时调用
                })