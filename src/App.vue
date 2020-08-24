<template>
  <div id="app">
    <tab-bar>
      <!-- activeColor="blue"动态转入一个颜色 -->
      <tab-bar-item path='/home' activeColor="deepPink">
        <!-- 不活跃时候的图标 -->
        <!-- <img slot="item-icon" src=""> -->
        <!-- 活跃时候的图标 -->
        <!-- <img slot="item-icon" src=""> -->
        <div slot="item-text">首页</div>
      </tab-bar-item>
      <tab-bar-item path="/category">
        <div slot="item-text">分类</div>
      </tab-bar-item>
      <tab-bar-item path="/cart">
        <div slot="item-text">购物车</div>
        </tab-bar-item>
      <tab-bar-item path="/profile">
        <div slot="item-text">我的</div>
      </tab-bar-item>
    </tab-bar>
    <router-view></router-view>
  </div>
</template>
<script>
import TabBar from './components/tabbar/TabBar';
import TabBarItem from './components/tabbar/TabBarItem';
export default {
  name:'App',
  components:{
    TabBar,
    TabBarItem,
    
  }
}
</script>

<style lang="scss">
//引入样式
  @import url(./assets/css/base.css);

  #tab-bar{
    display:flex;
    background-color: #f6f6f6;
    position: fixed;
    left: 0;
    right: 0;
    bottom: 0;
    box-shadow: 0px -3px 1px rgba(100,100,100,0.1);
  };
  .tab-bar-item{
    flex: 1;
    text-align: center;
    height: 49px;
  }
</style>
