<template>
  <div class="goods-box">
    <goods-list-item
      v-for="item in goods"
      :goodsItem="item"
      :key="item.goods"
    ></goods-list-item>
  </div>
</template>

<script>
import GoodsListItem from "./GoodsListItem";
export default {
  name: "GoodsList",
  props: {
    goods: {
      type: Array,
      default() {
        return [];
      }
    }
  },
  components: { GoodsListItem },
  data() {
    return {};
  },
  computed: {},
  watch: {},
  methods: {}
};
</script>

<style scoped>
.goods-box {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  padding: 4px;
}
</style>
