<template>
  <div id="app" class="container-fluid fill-height container-mask">
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
.fill-height{
  min-height: 100%;
  height: 100%;
}
.container-mask{
  padding: 0 !important;
  overflow: hidden;
}
</style>
