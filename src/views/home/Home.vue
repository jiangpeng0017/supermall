<template>
  <div id="home">
    <nav-bar class="home-nav">
      <div slot="center">购物街</div>
    </nav-bar>
    <home-swiper :banners="banners" />
    <recommend-view :recommends="recommends" />
    <feature-view></feature-view>
    <tab-control
      class="tab-control"
      :titles="['流行', '新款', '精选']"
    ></tab-control>

    <ul>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
      <li>44</li>
    </ul>
  </div>
</template>
<script>
import HomeSwiper from "./childComps/HomeSwiper";
import FeatureView from "./childComps/FeatureView";
import RecommendView from "./childComps/RecommendView";

import NavBar from "components/common/navbar/NavBar";
import TabControl from "../../components/content/tabcontrol/TabControl";

import { getHomeMultidata } from "network/home";

export default {
  name: "Home",
  components: { HomeSwiper, RecommendView, FeatureView, NavBar, TabControl },
  data() {
    return {
      banners: [],
      recommends: [],
      titles: [],
      goods: {
        pop: { page: 0, list: [] },
        news: { page: 0, list: [] },
        sell: { page: 0, list: [] }
      }
    };
  },
  created() {
    //1.请求多个数据
    getHomeMultidata().then(res => {
      this.banners = res.data.banner.list;
      this.recommends = res.data.recommend.list;
    });
  }
};
</script>

<style scoped>
#home {
  padding-top: 44px;
  padding-bottom: 49px;
}
.home-nav {
  background-color: var(--color-tint);
  color: #fff;
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  z-index: 9;
}
.tab-control {
  position: sticky;
  top: 44px;
  background: #fff;
}
</style>
