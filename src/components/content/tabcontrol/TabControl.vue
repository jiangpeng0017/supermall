<template>
  <div class="tab-control" >
    <div
      v-for="(item, index) in titles"
      class="tab-control-item"
      :key="item.title"
      :class="{ active: currentIndex === index }"
       @click="itemClick(index)"
    >
      <span>{{ item }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "TabControl",
  props: {
    titles: {
      type: Array,
      default() {
        return [];
      }
    }
  },
  data: function() {
    return {
      currentIndex: 0
    };
  },
  computed: {},
  watch: {},
  methods: {
    itemClick: function(index) {
      // 1.改变currentIndex
      this.currentIndex = index;
      // 2.发出事件
      this.$emit("itemClick", index);
    }
  }
};
</script>

<style scoped>
.tab-control {
  display: flex;
  text-align: center;
  line-height: 40px;
  font-size: 15px;
  background-color: #fff;
  z-index: 9;
}

.tab-control-item {
  flex: 1;
}

.tab-control-item span {
  padding: 5px;
}

.active {
  color: var(--color-high-text);
}

.active span {
  border-bottom: 2px solid var(--color-high-text);
}
</style>
