<template>
  <div class="wrap">
    <echarts :width="width" :height="height" :option="option"></echarts>
  </div>
</template>
<script>
import Echarts from "@/components/Echarts.vue";

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
      default: () => {
        return {
          title: {
            text: "自定义饼图",
            left: "center"
          },
          tooltip: {
            trigger: "item"
          },
        //   legend: {
        //     orient: "vertical",
        //     left: "left"
        //   },
          series: [
            {
              name: "访问来源",
              type: "pie",
              radius: "50%", // 饼图通过该属性控制展示位置
              center: ["50%", "50%"], // 饼图通过该属性控制展示位置
              roseType: 'radius',
              data: [
                { value: 1048, name: "搜索引擎" },
                { value: 735, name: "直接访问" },
                { value: 580, name: "邮件营销" },
                { value: 484, name: "联盟广告" },
                { value: 300, name: "视频广告" }
              ].sort(function (a, b) { return a.value - b.value; }),
              emphasis: {
                itemStyle: {
                  shadowBlur: 10,
                  shadowOffsetX: 0,
                  shadowColor: "rgba(0, 0, 0, 0.5)"
                }
              }
            }
          ]
        };
      }
    }
  },
  components: {
    Echarts
  },
  data() {
    return {};
  },
  mounted() {},
  methods: {}
};
</script>
<style scoped>
.wrap {
}
</style>