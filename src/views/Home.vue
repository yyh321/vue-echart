<template>
  <div class="home">
    <top-view />
    <sales-view />
    <bottom-view />
    <map-view />
  </div>
</template>

<script>
import TopView from '../components/TopView/index'
import SalesView from '../components/SalesView/index'
import MapView from '../components/MapView/index'
import BottomView from '../components/BottomView/index'

export default {
  name: 'Home',
  components: {
    TopView,
    BottomView,
    SalesView,
    MapView
  }
}
</script>

<style lang="scss" scoped>
  .home {
    width: 100%;
    height: 100%;
    background: #eee;
    padding: 20px;
    box-sizing: border-box;
  }
</style>
