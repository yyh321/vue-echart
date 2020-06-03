<template>
  <div class="top-view">
    <el-row :gutter="12">
      <el-col :span="6">
        <el-card shadow="always">
          <total-sales />
        </el-card>
      </el-col>
      <el-col :span="6">
        <el-card shadow="hover">
          <total-orders />
        </el-card>
      </el-col>
      <el-col :span="6">
        <el-card shadow="never">
          <today-users />
        </el-card>
      </el-col>
      <el-col :span="6">
        <el-card shadow="never">
          <total-users />
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import TotalSales from '../TotalSales/index'
import TotalOrders from '../TotalOrders/index'
import TodayUsers from '../TodayUsers/index'
import TotalUsers from '../TotalUsers/index'
export default {
  name: 'TopView',
  components: {
    TotalSales,
    TotalOrders,
    TodayUsers,
    TotalUsers
  }
}
</script>

<style lang="scss">
  .top-view {

  }
</style>
