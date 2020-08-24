<template>
  <div class="tab-bar-item" @click="itemClick">
      <!-- <div>首页</div> -->
      <!-- 不活跃时候的图标插槽
      <div v-if="!isActive"><slot name="item-icon"></slot></div> -->
      <!-- 活跃时候的图标
      <div v-else><slot name="item-icon-active"></div> -->
      <!-- 文字的插槽 -->
    <!-- <div :class="{active:isActive}"> -->
    <!-- <div class="active"> -->
    <div :style="activeStyle">
        <slot name="item-text"></slot>
    </div>
  </div>
</template>

<script>
export default {
    name:'TabBarItem',
    props:{
        path:String,
        activeColor:{
            type:String,
            default:'red'
        }
    },
    data(){
        return{
            // isActive:true,
            
            
        }
    },
    computed:{
        isActive(){
            //当前活跃的path是否包含自己定义的path
            console.log(this.path+"--"+this.$route.path.indexOf(this.path)!=-1);
            return this.$route.path.indexOf(this.path)!=-1;
        },
        activeStyle(){
            return this.isActive?{color:this.activeColor}:{};
        }
    },
    methods:{
        itemClick(){
            console.log(this.path+"--itemClick");
            this.$router.push(this.path);
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
    };
    /* .tab-bar-item img{
        width: 24px;
        height: 24px;
        margin-top: 3px;
        vertical-align: middle;
    }; */
    .active{
        color: red;
    }
</style>