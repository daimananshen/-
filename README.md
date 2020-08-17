#本项目仅供参考

#技术: uni-app + nodejs(或者 java)
 
**项目分析 1.0版本**

一、首页index
	1、顶部滑动导航栏
		封装：否
	2、头图
		名称：banner
		封装：是
	3、宫格
		名称：icons
		封装：是
	4、卡片
		名称：card
		封装：是 
		公用：否
	5、品牌
		名称：brand
		封装：否
	6、热销
		名称：hot
		封装：是
	7、店铺
		名称：shop
		封装：是
	8、为您推荐
		名称：
		封装：
	9、上拉加载
	
	
**公用的组件**
	1、单独的商品展示需要封装  名称：commodity  
		文字图片
	
	2、商品展示列表：commdityList
		内部调用：单独的商品调用
	
二、搜索：search
	1、最近搜索
		封装：否
	2、热门搜索
		封装：否
		
三、搜索列表 search-list
	1、商品列表
		封装：否
		
四、商品详情 detail
	1、头图滑动：swiper  	封装：是
	2、内容：content		封装：是
	3、看了又看 （调用商品展示列表）封装：是
	4、加入购物车 addCar	封装：是
	
五、购物车 shopCart  数据：vuex
	**检测登录**
	1、商品内容 封装：否	
	2、结算	封装：否
	
六、分类 list  封装：否
	
七、我的  myCenter
	**检测是否登录**
	
八、登录	
	
九、支付	
	
	
#目录结构
	manifest.json	配置文件:APPID、logo
	pages.json		配置文件:导航 、tabbar、路由
	main.js			Vue初始化文件
	app.vue			全局配置：全局方法、全局监听
	static			静态资源：图片、字体图标
	
	pages			页面
		index
			index.vue
		list
			list.vue
		myCenter
			myCenter.vue

	components   组件
		index
			banner.vue
			Icons.vue
		common
			commodity.vue
			
	common		公共文件：全局的css文件			
	

#字体图标
	放大镜、消息、删除、上下箭头、购物车
	
#tabbar图标
	首页、分类、购物车、我的
	
#注意点
	1、swiper组件不能取名swiper开头的，数据渲染过程中可能会导致图片消失。
	
	
	
	
	
	