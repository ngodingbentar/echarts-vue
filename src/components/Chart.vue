<template>
  <div>
    <v-chart class="chart" :option="option" />
    <v-chart class="chart" :option="optionBar" />
  </div>
</template>

<script>
import { use } from "echarts/core";
import { CanvasRenderer } from "echarts/renderers";
import { PieChart } from "echarts/charts";
import {
  TitleComponent,
  TooltipComponent,
  LegendComponent
} from "echarts/components";
import VChart from "vue-echarts";
import { ref, defineComponent } from "vue";

use([
  CanvasRenderer,
  PieChart,
  TitleComponent,
  TooltipComponent,
  LegendComponent
]);

export default defineComponent({
  name: "HelloWorld",
  components: {
    VChart
  },
  // provide: {
  //   [THEME_KEY]: "dark"
  // },
  setup () {
    const optionBar = ref({
      title: {
        text: "ECharts apa"
      },
      tooltip: {},
      // legend: {
      //   data: ["ga"]
      // },
      xAxis: {
        data: ["apple", "jambu", "manggis", "salak"]
      },
      yAxis: {
        type: "value"
      },
      series: [
        {
          name: "hah apa",
          type: "bar",
          data: [5, 20, 36, 10]
        }
      ]
    });
    const option = ref({
      title: {
        text: "Ngodingbentar",
        left: "center"
      },
      tooltip: {
        trigger: "item",
        formatter: "{a} <br/>{b} : {c} ({d}%)"
      },
      legend: {
        orient: "vertical",
        left: "left",
        data: ["Kos", "Investasi", "Hiburan", "Lainnya", "Makan"]
      },
      series: [
        {
          name: "Ngodingbentar",
          type: "pie",
          radius: "55%",
          center: ["50%", "60%"],
          data: [
            { value: 335, name: "Kos" },
            { value: 310, name: "Investasi" },
            { value: 234, name: "Hiburan" },
            { value: 135, name: "Lainnya" },
            { value: 1548, name: "Makan" }
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
    });

    return { option, optionBar };
  }
});
</script>

<style scoped>
.chart {
  height: 400px;
}
</style>