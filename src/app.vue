<template>
  <div class="side-bar" :style="{'background':BackgroundColor}">
    <ul :style="{color:color}">
      <li
        v-for="(item,index) in data"
        :key="index"
        :style="{
            'background' : activeIndex == index+1 ? activeBackgroundColor:'',
            'color': activeIndex == index+1 ? activeColor:'',
        }"
        v-on:click="$emit('click-sidebar', {e:this,item, activeIndex:index+1 })">
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
  },
};
</script>

<style lang="less" scoped>
*{
  margin: 0;
  padding: 0;
  list-style: none;
}
ul,
ol ,
li{
  list-style: none;
  margin: 0;
  padding: 0;
}

.side-bar {
  min-width: 80px;
  background: #010;
  ul {
    width: 100%;
    list-style: none;
    padding: 0;
    li {
      cursor: pointer;
      transform: all 0.5s;
      list-style: none;
      width: 100%;
      height: 80px;
      font-size: 14px;
      padding: 0;
      padding-top: 10px;
      box-sizing: border-box;
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