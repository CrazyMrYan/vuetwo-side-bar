[English](./README.md) 

# vuetwo-side-bar

> `vuetwo-side-bar` 使用的是vue2.0 配合 element图标 ，做的一个简洁的侧边栏



![](http://crazy.lovemysoul.vip/images/side-bar.gif)

## 下载

```shell
npm install vuetwo-side-bar
```



## 配合ElementUI-icon

因为本项目采用的字体库是`ElementUI`，如果你的项目是采用的 `ElementUI` 那么可以跳过这一步

``` html
<!-- 引入样式 -->
<link rel="stylesheet" href="https://unpkg.com/element-ui/lib/theme-chalk/index.css">
```

当然你也可以使用其他字体库的图标

例如：`Font Awesome` ,`iView`  都可以 ，原理都是一样，在 `i` 标签上面加上一个自己的类名



## 安装

```js
import VueSideBar from "vuetwo-side-bar";
&&
components: { VueSideBar },
```



**html**

```html
<VueSideBar
  :data="sidebar"
  :activeIndex="activeIndex"
  :color="color"
  :activeColor="activeColor"
  :BackgroundColor="BackgroundColor"
  :activeBackgroundColor="activeBackgroundColor"
  @click-sidebar="getClick"
></VueSideBar>
```

**js**

```js
sidebar: [
  {
    label: "概况",
    id: "1",
    icon: "el-icon-menu",
  },
  {
    label: "质量问题",
    id: "2",
    icon: "el-icon-info",
},
{
    label: "安全问题",
    id: "3",
    icon: "el-icon-error",
},
{
    label: "拆迁问题",
    id: "4",
    icon: "el-icon-s-flag",
},
{
    label: "工地视联",
    id: "5",
    icon: "el-icon-video-camera",
  },
],
activeIndex: 1,
color: "#fff",
activeColor: "#2196f3",
activeBackgroundColor: "rgba(255,255,255,.2)",
BackgroundColor: "rgb(44, 62, 80)",
```

**methods**

```js
getClick(data){
  this.activeIndex = data.activeIndex
},
```



## 参数

| name                  | type     | required | default              | describe     |
| --------------------- | -------- | -------- | -------------------- | ------------ |
| data                  | *Array*  | true     | []                   | 数据项       |
| activeIndex           | *Number* | true     | null                 | 选中的下标   |
| color                 | *String* | false    | #fff                 | 字体颜色     |
| BackgroundColor       | *String* | false    | #000                 | 背景颜色     |
| activeColor           | *String* | false    | #2196f3              | 选中字体颜色 |
| activeBackgroundColor | *String* | false    | rgba(255,255,255,.1) | 选中背景颜色 |
| type                  | *String* | false    | verticle             | 展示类型 `straight || verticle`     |



## 事件

* **click-sidebar**

  * 描述 : 点击之后返回当前选中的下标，以及选中数据项

  * 返回值：
    * data
      * `activeIndex` : 选中的下标
      * `item` : 选中的item

