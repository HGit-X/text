<template>
  <div class="tab-bar-item" @click="itemClick">
      <!-- <img src="../../assets/img/tabbar/home.png" alt="">
      <div>首页</div> -->
      <!-- <slot name="item-icon"></slot>
      <slot name="item-text"></slot> -->
        <div v-if="!isActive"> <slot name="item-icon"></slot></div>
        <div v-else> <slot name="item-icon-active"></slot></div>
        <div :style="activeStyle"> <slot name="item-text"></slot></div>
    </div>
</template>

<script>
export default {
  props: {
    path: String,
    activeColor: {
      type: String,
      default: 'red'
    }
  },
    data(){
        return{
            //isActive: true
        }
    },
    computed:{
      isActive() {
        //判断是不是该子组件处于活跃状态 
        return this.$route.path.indexOf(this.path) !== -1
      },
      activeStyle(){
        return this.isActive ? {color:this.activeColor}  : {}
      }
    },
    methods: {
      itemClick(){
        this.$router.replace(this.path)
      }
    }
}
</script>

<style>
  .tab-bar-item{
    flex: 1;
    text-align: center;
    height: 49px;
    font-size: 14px;
  }

  .tab-bar-item img {
    width: 24px;
    height: 24px;
    margin-top: 3px;
    vertical-align: middle;
    margin-bottom: 2px;
  }
</style>