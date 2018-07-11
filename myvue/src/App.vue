
<template>
  <div class="page-tabbar">
    <div class="page-wrap">
      <div class="page-title">Tabbar</div>
      <div>
        <mt-cell class="page-part" title="当前选中" :value="selected" />
      </div>
      <mt-header fixed title="足球商城"></mt-header>
      <!-- tabcontainer -->
      <mt-tab-container class="page-tabbar-container" v-model="selected">
        <mt-tab-container-item id="商品">
          <mt-cell v-for="n in 10" :title="'足球 ' + n" />
        </mt-tab-container-item>
        <mt-tab-container-item id="订单">
          <mt-cell v-for="n in 5" :title="'订单 ' + n" />
        </mt-tab-container-item>
        <mt-tab-container-item id="我的">
          <div class="page-part">
            <!-- cell -->
            <mt-cell v-for="n in 12" :title="'我的 ' + n" />
          </div>
          <router-link to="/">
            <!-- button -->
            <mt-button type="danger" size="large">退出</mt-button>
          </router-link>
        </mt-tab-container-item>
      </mt-tab-container>
    </div>

    <mt-tabbar v-model="selected" fixed>
      <mt-tab-item id="商品">
        <img slot="icon" src="./assets/sjb.png">
        商品
      </mt-tab-item>
      <mt-tab-item id="订单">
        <img slot="icon" src="./assets/sjb.png">
        订单
      </mt-tab-item>
      <mt-tab-item id="我的">
        <img slot="icon" src="./assets/sjb.png">
        我的
      </mt-tab-item>
    </mt-tabbar>
  </div>
</template>

<script>
  import MtHeader from "mint-ui/packages/header/src/header";

  export default {
    components: {MtHeader},
    name: 'page-tabbar',
    data() {
      return {
        selected: '商品'
      };
    }
  };
</script>

<style>
  .page-tabbar {
    overflow: hidden;
    height: 100vh;
  }

  .page-wrap {
    overflow: auto;
    height: 100%;
    padding-bottom: 100px;
  }
</style>
