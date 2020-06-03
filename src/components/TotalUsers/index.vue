<template>
  <div class="total-users">
    <common-card title="累计用户数" value="1,087,503">
      <template>
        <div id="total-user-chart" :style="{width: '100%',height:'100%'}"></div>
      </template>
      <template v-slot:footer>
        <div class="total-user-footer">
          <span>日同比 </span>
          <span class="emphasis">8.73%</span>
          <div class="increase"></div>
            <span class="month">月同比 </span>
            <span class="emphasis">35.91%</span>
            <div class="decrease"></div>
        </div>
      </template>
    </common-card>
  </div>
</template>

<script>
import commonCardMixin from '../../mixins/commonCardMixin'
export default {
  name: 'TotalUsers',
  mixins: [commonCardMixin],
  mounted () {
    const chartDom = document.getElementById('total-user-chart')
    const chart = this.$echarts.init(chartDom)
    chart.setOption({
      grid: {
        top: 0,
        bottom: 0,
        left: 0,
        right: 0
      },
      xAxis: { type: 'value', show: false },
      yAxis: { type: 'category', show: false },
      series: [{
        type: 'bar',
        stack: '总量',
        data: [150],
        barWidth: 10,
        itemStyle: {
          color: '#45c946'
        }
      }, {
        type: 'bar',
        data: [250],
        stack: '总量',
        itemStyle: {
          color: '#eee'
        }
      }, {
        type: 'custom',
        data: [150],
        stack: '总量',
        renderItem: (params, api) => {
          const value = api.value(0)
          const endPoint = api.coord([value, 0])
          return {
            type: 'group',
            position: endPoint,
            children: [
              {
                type: 'path',
                shape: {
                  d: 'M163.396608 289.168384c-40.577024 0-66.526208 54.183936-35.44064 85.25824L477.217792 723.704832c20.031488 20.031488 49.82272 20.031488 69.853184 0l349.274112-349.278208c30.30528-30.294016 6.677504-85.25824-34.927616-85.25824L163.396608 289.168384z',
                  x: -5,
                  y: -15,
                  width: 10,
                  height: 10,
                  layout: 'cover'
                },
                style: {
                  fill: '#45c946'
                }
              },
              {
                type: 'path',
                shape: {
                  d: 'M131.974144 648.752128c-30.418944 30.430208-6.474752 84.301824 34.917376 84.301824L858.258432 733.053952c42.899456 0 65.325056-53.85216 34.916352-84.301824L547.487744 302.569472c-19.930112-19.974144-49.374208-19.95264-69.327872 0L131.974144 648.752128z',
                  x: -5,
                  y: 5,
                  width: 10,
                  height: 10,
                  layout: 'cover'
                },
                style: {
                  fill: '#45c946'
                }
              }
            ]
          }
        }
      }]
    })
  }
}
</script>

<style lang="scss" scoped>
  .total-user-footer {
    display: flex;
    align-items: center;
    .month {
      margin-left: 5px;
    }
  }
</style>
