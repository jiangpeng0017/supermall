<template>
  <div class="wrapper" ref="aaaa">
    <ul class="content">
      <button class="btn" @click="btnClick">按钮</button>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
      <li>分类的列表</li>
    </ul>
  </div>
</template>

<script>
import BScroll from "better-scroll";

export default {
  name: "Category",
  components: {},

  data() {
    return {
      scroll: null
    };
  },
  // 组件创建完调用
  created() {},
  mounted() {
    this.scroll = new BScroll(this.$refs.aaaa, {
      probeType: 3,
      pullUpLoad: true
    });

    this.scroll.on("scroll", position => {
  
    });
    this.scroll.on("pullingUp", () => {
      // console.log("上啦加载更肥");
    });
  },
  computed: {},
  methods: {
    btnClick() {
     console.log('btnClick');
     
    }
  }
};
</script>

<style scoped>
.wrapper {
  height: 150px;
  background: red;
  overflow: hidden;
}
</style>
