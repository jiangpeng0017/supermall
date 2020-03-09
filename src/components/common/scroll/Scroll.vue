<template>
  <!--ref/childreb -->
  <div ref="wrapper">
    <div class="content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
import BScroll from "better-scroll";

export default {
  name: "Scroll",
  props: {
    probeType: {
      type: Number,
      default: 1
    },
    // pullUpLoad: {
    //   type: Boolean,
    //   default: false
    // }
  },
  data() {
    return {
      scroll: {}
    };
  },
  mounted() {
    // 1.初始化BScroll对象
    this.scroll = new BScroll(this.$refs.wrapper, {
      probeType: this.probeType,
      click: true,
      pullUpLoad: this.pullUpLoad
    });
    // 2.将监听事件回调
    this.scroll.on("scroll", position => {
      this.$emit("scroll", position);
    });

    // 3.监听上拉事件
    // this.scroll.on("pullingUp", () => {
    //   this.$emit("pullingUp");
    // });
  },
  methods: {
    scrollTo(x, y, time) {
      this.scroll.scrollTo(x, y, time);
    },
    finishPullUp() {
      this.scroll.finishPullUp();
    },
    refresh() {
      this.scroll.refresh();
    }
  },
  watch: {}
};
</script>

<style scoped>
</style>
