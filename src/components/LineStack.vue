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
            text: "堆叠面积图",
            textAlign: "auto"
          },
          tooltip: {
            trigger: "axis",
            axisPointer: {
              type: "cross",
              label: {
                backgroundColor: "#6a7985"
              }
            }
          },
          legend: {
            data: ["邮件营销", "联盟广告", "视频广告", "直接访问", "搜索引擎"],
            top: 28,
            left: 80,
            itemHeight: 8
          },
          grid: {
            left: 0,
            bottom: 0,
            containLabel: true
          },
          toolbox: {
            feature: {
              saveAsImage: {}
            }
          },
          xAxis: [
            {
              type: "category",
              data: ["周一", "周二", "周三", "周四", "周五", "周六", "周日"]
            }
          ],
          yAxis: [
            {
              type: "value",
              axisTick: {
                show: true
              },
              axisLine: {
                show: true
              },
              name: "单位：MB"
            }
          ],
          series: [
            {
              name: "邮件营销",
              type: "line",
              stack: "总量",
              areaStyle: {},
              emphasis: {
                focus: "series"
              },
              symbol: "circle",
              data: [120, 132, 101, 134, 90, 230, 210]
            },
            {
              name: "联盟广告",
              type: "line",
              stack: "总量",
              areaStyle: {},
              emphasis: {
                focus: "series"
              },
              data: [220, 182, 191, 234, 290, 330, 310]
            },
            {
              name: "视频广告",
              type: "line",
              stack: "总量",
              areaStyle: {},
              emphasis: {
                focus: "series"
              },
              data: [150, 232, 201, 154, 190, 330, 410]
            },
            {
              name: "直接访问",
              type: "line",
              stack: "总量",
              areaStyle: {},
              emphasis: {
                focus: "series"
              },
              data: [320, 332, 301, 334, 390, 330, 320]
            },
            {
              name: "搜索引擎",
              type: "line",
              stack: "总量",
              areaStyle: {},
              emphasis: {
                focus: "series"
              },
              data: [820, 932, 901, 934, 1290, 1330, 1320]
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