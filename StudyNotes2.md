#wxss之flex布局#
##wxss#
###尺寸单位  
小程序规定了全新的尺寸单位“rpx”,  其原理是无视设备原先的尺寸，  统一规定屏幕宽度为750rpx。  
换算：    
iPhone5				1rpx=0.42px  
iPhone6				1rpx=0.5px  
iPhone6 Plus			1rpx=0.522px  
***
###常用属性
background-color  :  背景色  
color   :				前景色  
font-size    :     	字体大小  
border   :     边框  
width   :    宽度  
height  :    高度  
***
###内联样式
* style   
`<view style=”color:red;background-color:yellow”>测试</view> `   
* class  
  如之前所使用
***
###flex布局
* 基本概念  
    >容器和项目  
坐标轴  
* 容器属性
    >1.flex-direction：用于设置主轴方向，通过设置坐标轴可以规定项目的排列方向  
     语法格式:
    `.container{  
     display:flex;  
     flex-direction: row(默认）|row-reverse|column|column-reverse;  
      }`

     row:默认值，主轴在水平方向上从左到右，项目按照主轴方向从左到右排列  
    row-reverse:主轴是row的反方向，项目按照主轴方向从右到左排列  
    column:主轴在垂直方向上从上而下，项目按照主轴方向从上往下排列  
    column-reverse:主轴是column的反方向，项目按照主轴方向从下往上排列  
     >2.justify-content：用于设置项目在主轴方向上的对齐方式，以及分配项目之间及其周围多余的空间  
    语法格式: 
    `.container{
display:flex;
justify-content:flex-start(默认值)|flex-end|center|space-around|space-between
}
flex-start:默认值，表示项目对齐主轴起点，项目间不留空隙
center:项目在主轴上居中排列，项目间不留空隙。主轴上第一个项目离主轴起点的距离等于最后一个项目离主轴终点的距离
flex-end：项目对齐主轴终点，项目间不留空隙
space-between：项目间距相等，第一个和最后一个项目分别离起点/终点的距离为0
space-around：与space-between相似，不同之处为第一个项目离主轴七点和最后一个项目离终点的距离为中间项目间距的一半` 

    >3.align-items：用于设置项目在行中的对齐方式  
    语法格式：
    `.container{
display:flex;
align-items:stretch(默认值)|flex-start|center|flex-end;
}
stretch:默认值，未设置项目尺寸时将项目拉伸至填满交叉轴
flex-start：项目顶部与交叉轴起点对齐
center：项目在交叉轴居中对齐
flex-end：项目底部与交叉轴终点对齐`

    >4.align-content：用于多行排列时设置项目在交叉轴方向上的对齐方式，以及分配项目之间及其周围多余的空间。  
    语法格式：
    `.container{
display:flex;
align-content: stretch(默认值)|flex-start|center|flex-end|space-around|space-between;
}
stretch：默认值，未设置项目尺寸时将各行中的项目拉伸至填满交叉轴。当设置了项目尺寸时项目尺寸不变，项目行拉伸至填满交叉轴
flex-start：首行在交叉轴起点开始排列，行间不留间距
center：行在交叉轴终点开始排列，行间不留间距，首行离交叉轴起点和行尾离交叉轴终点的距离相等
flex-end：尾行在交叉轴终点开始排列，行间不留间距
space-around：行与行间距相等，首行离交叉轴起点和尾行离交叉轴终点的距离为行与行间间距的一半。
space-between：行间间距、首行离交叉轴起点和尾行离交叉轴终点的距离相等
5.flex-wrap：用于规定是否允许项目换行，以及多行排列时换行的方向。`

* 项目属性  
    >1.order属性：  
    >用于设置项目沿主轴方向上的排列顺序，数值越小，排列越靠前。另外，该属性值为整数。  
   语法格式：
    `.item{
order:0(默认值)|<integer>
}
2.flex-shrink属性：用于设置项目收缩因子。当项目在主轴方向上溢出时，通过项目收缩因子的规定比例压缩项目以适应容器。
.item{
flex-shrink:1(默认值)|<number>
}`

  提示：其属性值为项目的收缩因子，只能是非负数。  
  当发生溢出时，项目尺寸的收缩公式如下：  
最终长度=原长度x(1-溢出长度x收缩因子/压缩总权重)  
压缩总权重=长度1x收缩因子1+长度2x收缩因子2+……+长度Nx收缩因子N  
注意：当遇到小数的情况时向下取整，不进行四舍五入  
   当从左往右为主轴时，长度指的是宽度；当从上往下为主轴时，长度指的是高度。  
需要注意：只有项目的flex-shrink属性值总和大于1时溢出长度按照实际计算，当总和小于1时溢出长度的计算公式如下：  
溢出长度=实际溢出长度x(收缩因子1+收缩因子2+……+收缩因子N)
***
###flex-grow属性：  
**用于设置项目扩张因子。当项目在主轴方向上还有剩余空间时，通过设置项目扩张因子进行剩余空间的分配。**  
语法格式  
    `.item{
flex-grow:0(默认值)|<number>
}`

提示：其属性值为项目的扩张因子，只能是非负数  
   当发生扩张时，项目尺寸的扩张公式如下：  
最终长度=原长度+扩张单位x扩张因子  
注意：当遇到小数的情况时向下取整，不进行四舍五入  
当从左往右为主轴时，长度指的是宽度；当从上往下为主轴时，长度指的是高度。  
ps:扩张单位=剩余空间/(扩张因子1+扩张因子2+……+扩张因子N)  
需要注意的是：只有项目的flex-grow属性值总和大于1时扩张单位按照实际计算，当总和小于1时扩张单位就是全部的剩余空间。 
*** 
###flex-basis属性：  
**根据主轴方向代替项目的宽或高**，具体说明如下：
* 当容器设置flex-direction为row或row-reverse时，若项目的flex-basis和width属性同时存在数值，则flex-basis代替width属性。
* 当容器设置flex-direction为colume或column-reverse时，若项目的flex-basis和height属性同时存在数值，则flex-basis代替项目的height属性。  
语法格式：
    `.item{
flex-basis:auto(默认值)|<number>px
}`
***
###align-self属性：  
**设置项目在行中交叉轴方向上的对齐方式，用于覆盖容器的align-items，这么做可以对项目的对齐方式做特殊处理。**  
语法格式：  
    `.item{
align-self:auto(默认值)|flex-start|center|flex-end|baseline|strech
}`


