#小程序开发学习笔记  
##页面创建



- 全局三个文件，分别是APP.JS  APP.JSON  APP.WXSS(名称不可更改）

- 创建PAGES目录文件（作用是用来放各个页面的）

- 创建页面(给页面起名字，并且创建4个文件)
	
    JS：页面逻辑实现
	
    JSON: 负责标题栏和一些状态栏
	
    WXML: 管理页面有什么
	
    WXSS: 页面排布

- 把内容单元封装在view内部，写法`<view>"内容”</view>`
	
    用CLASS的方法对view内容样式进行排布

	……CLASS可以对其他组件样式布局也有效，CLASS规定的样式前需要加上'.'，如果像image/text这样的组件的话，不需要加'.'(全局有效）


- 三个组件：图片`<image src='图片路径'></image>`、文字`<text>"内容"</text>`、按钮`<button >"按钮上的字"</button>`

##picker组件


 `<picker>`是从底部弹起的滚动选择器组件，目前根据mode属性值的不同共支持5种选择器，  
  分别是普通选择器，多列选择器，时间选择器，日期选择器，省市区选择器。  
  若省略mode值不写，则默认效果是普通选择器。  
  **省市区选择器**  
  当mode=’region’时为省市区选择器效果（最低版本为1.4.0） 
##网络API
 和风天气：提供的API接口  
根据网站的相关代码提示和接口信息制作url  
回到微信公众平台，添加服务器域名   

- 调用函数：this."函数名"(参数列表)  
   

- `wx.requst({
   url: 
   data:  
   success:function(e){  
通常先在控制台输出查看一下  
      }  
})`  
+
更改变量值
