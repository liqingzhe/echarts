<template>
  <div :style="'width:' + width + 'px;height:' + height + 'px;'" ref="echarts"></div>
</template>
<script>
import * as echarts from "echarts";

export default {
  props: {
    width: {
      type: Number,
      default: 300
    },
    height: {
      type: Number,
      default: 200
    },
    option: {
      type: Object,
      default: () => {}
    }
  },
  data() {
    return {};
  },
  mounted() {
    const dom = this.$refs.echarts;
    const chart = echarts.init(dom);
    chart.setOption(this.option);
  },
  methods: {}
};
</script>
<style scoped>
.wrap {
}
</style>