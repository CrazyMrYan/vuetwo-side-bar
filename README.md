[简体中文](./README.zh-CN.md) 

# vuetwo-side-bar

>This plugin is a simple sidebar made with  `VUE2.0`



![](http://crazy.lovemysoul.vip/images/side-bar.gif)

## install

```shell
npm install vuetwo-side-bar
```



## use

```js
import VueSideBar from "vuetwo-side-bar";
&&
components: { VueSideBar },
```



## coordinate ElementUI-icon

Because the font library used in this project is `ElementUI `,  you can skip this step if your project is using `ElementUI`

```html
<!-- The introduction of the style -->
<link rel="stylesheet" href="https://unpkg.com/element-ui/lib/theme-chalk/index.css">
```

Of course, you can also use ICONS from other font libraries

For example: `Font Awesome`, `iView` can be, the principle is the same, `I` tag with its own class name



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



## parameter

| name                  | type     | required | default              | describe                    |
| --------------------- | -------- | -------- | -------------------- | --------------------------- |
| data                  | *Array*  | true     | []                   | data item                   |
| activeIndex           | *Number* | true     | null                 | Select the subscript        |
| color                 | *String* | false    | #fff                 | font color                  |
| BackgroundColor       | *String* | false    | #000                 | background color            |
| activeColor           | *String* | false    | \#2196f3             | Select the color            |
| activeBackgroundColor | *String* | false    | rgba(255,255,255,.1) | Select the background color |



## event

* **click-sidebar**

  * describe : Clicking returns the index and data of the selected item

  * returned value
    * data
      * `activeIndex` : Select the subscript
      * `item` : Select data item

