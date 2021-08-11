<template>
  <div class="wrap">
    <echarts :width="width" :height="height" :option="option"></echarts>
  </div>
</template>
<script>
import Echarts from "@/components/Echarts.vue";
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
      default: () => {
        return {
          title: {
            text: "柱状图-数据堆叠",
            textStyle: {
              color: "#333",
              fontStyle: "oblique"
            }
          },
          tooltip: {},
          legend: {
            icon: "rect",
            data: ["视频广告", "直接访问", "搜索引擎"],
            top: 30,
            left: 40,
            itemHeight: 8,
            itemWidth: 8
          },
          grid: {
            containLabel: true,
            bottom: 20
          },
          xAxis: {
            type: "value",
            axisTick: {
              show: true
            },
            splitLine: {
              show: true
            }
          },
          yAxis: {
            type: "category",
            axisTick: {
              show: true
            },
            axisLine: {
              show: true
            },
            splitLine: {
              show: true
            },
            data: ["周一", "周二", "周三", "周四", "周五", "周六", "周日"]
          },
          series: [
            {
              name: "视频广告",
              type: "bar",
              label: {
                show: true
              },
              itemStyle: {
                color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [
                  { offset: 0, color: "#83bff6" },
                  { offset: 0.5, color: "#188df0" },
                  { offset: 1, color: "#188df0" }
                ])
              },
              stack: "total",
              emphasis: {
                focus: "series"
              },
              data: [5, 20, 36, 10, 10, 20, 12]
            },
            {
              name: "直接访问",
              type: "bar",
              label: {
                show: true
              },
              stack: "total",
              emphasis: {
                focus: "series"
              },
              data: [15, 5, 6, 55, 9, 21, 9]
            },
            {
              name: "搜索引擎",
              type: "bar",
              label: {
                show: true
              },
              stack: "total",
              emphasis: {
                focus: "series"
              },
              data: [6, 24, 6, 40, 7, 10, 4]
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