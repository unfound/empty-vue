<template>
    <div class="highcharts"></div>
</template>

<script>
import Highcharts from 'highcharts/highstock'
import HighchartsMore from 'highcharts/highcharts-more'
import HighchartsDrilldown from 'highcharts/modules/drilldown'
import Highcharts3D from 'highcharts/highcharts-3d'
import Highmaps from 'highcharts/modules/map'

HighchartsMore(Highcharts)
HighchartsDrilldown(Highcharts)
Highcharts3D(Highcharts)
Highmaps(Highcharts)

export default {
  props: ['options', 'styles'],
  name: 'highcharts',
  data () {
    return {
      chart: null
    }
  },
  mounted () {
    this.initChart()
  },
  methods: {
    initChart () {
      console.log(this.$el)
      this.$el.style.width = (this.styles.width || 800) + 'px'
      this.$el.style.width = (this.styles.width || 800) + 'px'
      this.chart = new Highcharts.Chart(this.$el, this.options)
    }
  }
}
</script>

<style lang="less">
.highcharts {
    width: 800px;
    height: 400px;
}
</style>
