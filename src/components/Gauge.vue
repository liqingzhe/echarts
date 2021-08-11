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
            text: "仪表盘"
          },
          series: [
            {
              type: "gauge",
              //   startAngle: 180, // 半圆形设置
              //   endAngle: 0,
              pointer: {
                //指针
                // icon:
                //   "path://M2090.36389,615.30999 L2090.36389,615.30999 C2091.48372,615.30999 2092.40383,616.194028 2092.44859,617.312956 L2096.90698,728.755929 C2097.05155,732.369577 2094.2393,735.416212 2090.62566,735.56078 C2090.53845,735.564269 2090.45117,735.566014 2090.36389,735.566014 L2090.36389,735.566014 C2086.74736,735.566014 2083.81557,732.63423 2083.81557,729.017692 C2083.81557,728.930412 2083.81732,728.84314 2083.82081,728.755929 L2088.2792,617.312956 C2088.32396,616.194028 2089.24407,615.30999 2090.36389,615.30999 Z",
                // length: "70%",
                // width: 16,
                // offsetCenter: [0, 0]
                itemStyle: {
                  color: "auto"
                }
              },
              anchor: {
                // 指针固定点
                show: true,
                showAbove: true,
                size: 10,
                itemStyle: {
                  borderColor: "red",
                  borderWidth: 10
                }
              },
              axisLabel: {
                distance: 20,
                color: "auto",
                fontSize: 12
              },
              axisLine: {
                lineStyle: {
                  width: 14,
                  color: [
                    [0.2, "#c23531"],
                    [0.6, "#63869e"],
                    [1, "#91c7ae"]
                  ]
                }
              },
              axisTick: {
                distance: -14,
                length: 6,
                lineStyle: {
                  color: "#fff",
                  width: 1
                }
              },
              splitLine: {
                length: 14,
                distance: -14,
                lineStyle: {
                  width: 1,
                  color: "#fff"
                }
              },
              title: {
                // detail的标题内容-完成率
                offsetCenter: [0, "-40%"],
                fontSize: 14
              },
              detail: {
                valueAnimation: true,
                fontSize: 30,
                formatter: function(value) {
                  return "{value|" + value.toFixed(0) + "\n}{unit|km/h}";
                },
                offsetCenter: [0, "70%"],
                rich: {
                  value: {
                    fontSize: 30,
                    fontWeight: "bolder",
                  },
                  unit: {
                    fontSize: 14,
                    color: "#999",
                    padding: [-15, 0, 0, 0]
                  }
                }
              },
              data: [
                {
                  value: 10,
                  name: "节点1"
                }
              ]
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
</style>