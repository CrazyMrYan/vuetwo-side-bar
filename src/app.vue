<template>
  <div :class="type" :style="{'background':BackgroundColor}">
    <ul :style="{color:color}">
      <li
        v-for="(item,index) in data"
        :key="index"
        :style="{
            'background' : activeIndex == index+1 ? activeBackgroundColor:'',
            'color': activeIndex == index+1 ? activeColor:'',
        }"
        v-on:click="(e, d,i) => $emit('click-sidebar', e,data[index], index+1)"
        v-on:mouseover="(e, d,i) => $emit('click-mouseover', e,data[index], index+1)"
        v-on:mouseout="(e, d,i) => $emit('click-mouseout', e,data[index], index+1)"
      >
        <p>
          <i :class="item.icon"></i>
        </p>
        {{item.label}}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    data: {
      type: Array,
      default: new Array(),
      required: true,
    },
    activeIndex: {
      type: Number,
      required: true,
    },
    color: {
      type: String,
      required: false,
      default: "#fff",
    },
    activeBackgroundColor: {
      type: String,
      required: false,
      default: "rgba(255,255,255,.1)",
    },
    activeColor: {
      type: String,
      required: false,
      default: "#2196f3",
    },
    BackgroundColor: {
      type: String,
      required: false,
      default: "#000",
    },
    type: {
      type: String,
      required: false,
      default: "verticle",
    },
  },
};
</script>

<style lang="less" scoped>
* {
  margin: 0;
  padding: 0;
  list-style: none;
}
ul,
ol,
li {
  list-style: none;
  margin: 0;
  padding: 0;
}
.straight {
  min-width: 140px;
  ul {
    width: 100%;
    li {
      cursor: pointer;
      transition: all .3s;
      width: 100%;
      height: 50px;
      line-height: 50px;
      font-size: 16px;
      padding-left: 20px;
      box-sizing: border-box;
      box-sizing: border-box;
      display: flex;
      justify-items: center;
      align-items: center;
      p {
        font-weight: 600;
        font-size: 16px;
        width: 24px;
        line-height: 50px;
        vertical-align: middle;
      }
    }
  }
}
.verticle {
  min-width: 80px;
  background: #010;
  ul {
    width: 100%;
    list-style: none;
    padding: 0;
    li {
      cursor: pointer;
      list-style: none;
      width: 100%;
      height: 80px;
      font-size: 14px;
      padding: 0;
      padding-top: 10px;
	  box-sizing: border-box;
	  transition: all .3s;
      p {
        font-weight: 600;
        font-size: 34px;
        line-height: 40px;
        height: 40px;
      }
    }
  }
}
</style>