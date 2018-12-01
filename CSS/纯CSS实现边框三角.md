### 边框三角的实现原理： 
相连两条边框如果颜色不一样，就会出现一个斜角,，利用这个斜角，我们就可以轻松实现一个三角形
<br/>

**案例一：元素宽高300，边框宽度均为50，上下边框为黄色，左右边框为红色，需要实现一个朝上的三角形**
```javascript
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=script, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        .triangle {
            height: 300px;
            width: 300px;
            border: 50px solid yellow;
            border-left: 50px solid red;
            border-right: 50px solid red;
        }
    </style>
</head>

<body>
    <div class="triangle"></div>
</body>

</html>

```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181201162507733.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzQxMDQxOQ==,size_16,color_FFFFFF,t_70)

<br/>
<hr/>

### 边框三角实现思路
1.元素宽高为0，这时候我们可以看到4个三角形

![在这里插入图片描述](https://img-blog.csdnimg.cn/20181201163513885.png)

2.如果是需要三角形 3，也就是说2号和4号的颜色应该是透明的（也就是左边框和右边框）的边框颜色为transparent，并且1号（也就是上边框的边框为0）
```javascript
.triangle {
   height: 0px;
   width: 0px;
   border: 50px solid yellow;
   border-top:0;
   border-left: 50px solid transparent;
   border-right: 50px solid transparent;
}
```

3.得到三角形

![在这里插入图片描述](https://img-blog.csdnimg.cn/20181201164350390.png)


<br/>

### 如何设计三角形的样式

根据上面的演变，我们可以看出：

**三角形的高 = 相应边框的border-width** (比如，我们刚刚要的事下边框所组成的三角形，所以这个三角形的高就是下边框的border-width)

**三角形的底边长 = border-color为相连两条边框之和**，也就是transparent的两条边框（在上面的例子中就是左边框的border-width + 右边框的border-width）

**三角形的颜色 = 相应边框的border-color**（上面的例子，就是底边框的颜色）


### 总结：
1、将元素的宽高都设置为0<br/>
2、三角形的尖尖是哪个方向的，哪个方向的边框就为0<br/>
3、三角形的底边长就是相连两条边的边框之和<br/>
4、三角形的高就是所选取的这条边的边框宽度<br/>
5、三角形的颜色就是所选取的这条边的边框颜色<br/>
