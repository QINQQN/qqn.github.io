---
layout: post
title: Jekyll搭建个人博客
date: 2016-10-14 
tags: 博客   
---


这里将介绍下微信小程序 动画
     

### 上代码:1.html
<view  class="view_a">  
2.<image animation="{{animation}}" class="a_img" src="https://img-blog.csdn.net/20170614190537974?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvVUZPMDAwMDE=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center"></image>  
3.</view>  
4.<view class="sure" bindtap="dh">发射</view>  

### 2.css

.sure{  
2.  width: 10%;  
3.  height:80rpx;  
4.  margin-top: 0rpx;  
5.  margin-left: 45%;  
6.  background: #00ddff;  
7.  border-radius: 50rpx;  
8.  text-align: center;  
9.  line-height: 80rpx;  
10.  color: #fff;  
11.}  
12..view_a{  
13.  width: 100%;  
14.  height: 900rpx;  
15.  display: flex;  
16.  background-image: url('https://img-blog.csdn.net/20170615103714645?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvVUZPMDAwMDE=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center');  
17.}  
18..a_img{  
19.  margin-top: 600rpx;  
20.  margin-left:100rpx;  
21.  width: 80rpx;  
22.  height:80rpx;  
23.}  
### 3.javascript
data: {  
2.    animation : ''  
3. },  
4. dh: function(){  
5.    var that = this;  
6.     //实例化  
7.     that.animation = wx.createAnimation({  
8.       duration: 200,  
9.       timingFunction: "ease",  
10.       delay: 1000,  
11.       transformOrigin: 'center',  
12.       success: function (res) {  
13.         console.log(res)  
14.       }  
15.     })  
16.     that.animation  
17.     .rotate(180).step()   //原点顺时针旋转180度  也可以不加.step() 不加的话便是动画同时执行  
18.     .rotate(-180).step()  //原点逆时针旋转180度  
19.     .rotate(0).step()     //回到初始  
20.     .scale(1.3).step()    // x,y轴同时缩放1.3倍  
21.     .translateX(90).step()//x轴偏移90px  
22.     .translateY(20).step()//y轴偏移20px  
23.     .skew(30).step()      //x轴沿顺时针偏移30度  
24.     .skew(-30).step()     //x轴沿逆时针偏移30度  
25.     .skew(0).step()       //返回不偏移时  
26.     .rotateY(180).step()  //Y轴旋转180度  
27.     .translateY(-222).step()//在y轴偏移-222px  
28.     .matrix3d(0.8, 0, 28).step();  
29.     that.setData({  
30.       animation: that.animation.export()  
31.     })},  
