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
            text: "某站点用户访问来源",
            subtext: "纯属虚构",
            left: "center"
          },
          tooltip: {
            trigger: "item"
          },
          legend: {
            orient: "vertical",
            right: 10,
            textStyle: {
                fontSize: 12
            } 
          },
          series: [
            {
              name: "访问来源",
              type: "pie",
              radius: ["40%", '70%'], // 饼图通过该属性控制展示位置
              center: ["35%", "60%"], // 饼图通过该属性控制展示位置
              data: [
                { value: 1048, name: "搜索引擎" },
                { value: 735, name: "直接访问" },
                { value: 580, name: "邮件营销" },
                { value: 484, name: "联盟广告" },
                { value: 300, name: "视频广告" }
              ],
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