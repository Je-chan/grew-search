<template>
  <highcharts :options="chartOptions" />
</template>

<script>
import { Chart } from 'highcharts-vue';
import {testChartOptions} from '~/utilities/chart/options/testChartOptions.js';
import { defineComponent } from 'vue';

export default defineComponent({
  components: {
    highcharts: Chart,
  },
  props: {
    title: {
      type: String,
      default: ''
    },
    type : {
      type: String,
      default: 'line'
    },
    xAxisList: {
      type: Array,
      default: () => []
    },
    yAxisUnit: {
      type: String,
      default: '',
    },
    yAxisData: {
      type: Array,
      default: () => [],
    },
    yAxisDataName: {
      type: String,
      default: 'example'
    },
    chartColor: {
      type: String,
      default: '#7EB923'
    },
    tooltipClear: {
      type: Boolean,
      default: false
    }
  },
  setup(props) {

    const chartOptions = testChartOptions(props.title, props.type, props.xAxisList, props.yAxisUnit, props.yAxisData, props.yAxisDataName, props.chartColor, props.tooltipClear);




    return {
      chartOptions,
    };
  }
});
</script>
<style lang="scss" scoped>
</style>
