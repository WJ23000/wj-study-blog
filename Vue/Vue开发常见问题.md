# 常用问题

## 问题1：改变数组页面没渲染
```
解决方法1：使用this.$set(原数组，位置，new值)改变数组
解决方法2：复制数组到一个新的变量，对变量进行操作，然后数组=改变后的变量
```

## 问题2：页面渲染需要同时使用v-if和v-for时(v-for比v-if优先级高,会导致v-if重复渲染)
```
错误代码：<div v-if="item.status",v-for="(item,index) in arrList",:key="index"></div>
解决方法：将v-if和v-for分开使用
```

## 问题3：img绑定的src找不到图片导致页面渲染异常
> imgUrlDefault = require("../assets/image/a.png")
解决方法1：
> <img :src="item.imgUrl | imgUrlDefault"/>
解决方法2：
> <img :src="resetImg(item.imgUrl)"/>
> resetImg(img){
>    if(img) {
>        return img
>    } else {
>        return imgUrlDefault
>    }
> }
```