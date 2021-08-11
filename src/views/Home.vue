<template>
  <el-container>
    <el-aside width="400px">
      <bar :width="400" :height="200" />
      <bar-stack :width="400" :height="220" />
      <gauge :width="400" :height="220" />
      <gauge-grade :width="400" :height="220" />
    </el-aside>
    <el-main>
      <line-chart :width="580" :height="270" />
      <line-stack :width="580" :height="270" />
    </el-main>
    <el-aside width="400px">
      <pie :width="400" :height="240" />
      <pie-custom :width="400" :height="240" />
    </el-aside>
  </el-container>
</template>

<script>
// @ is an alias to /src
import Bar from "@/components/Bar.vue";
import BarStack from "@/components/BarStack.vue";
import Pie from "@/components/Pie.vue";
import PieCustom from "@/components/PieCustom.vue";
import LineChart from "@/components/Line.vue";
import LineStack from "@/components/LineStack.vue";
import Gauge from "@/components/Gauge.vue";
import GaugeGrade from "@/components/GaugeGrade.vue";

export default {
  name: "Home",
  components: {
    Bar,
    BarStack,
    LineChart,
    LineStack,
    Pie,
    PieCustom,
    Gauge,
    GaugeGrade
  }
};
</script>
<style scoped>
.el-main {
  padding: 0;
}
.wrap {
  margin: 10px;
}
</style>
