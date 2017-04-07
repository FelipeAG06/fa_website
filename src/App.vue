<template>
  <div id="app" class="container-fluid fill-height container-mask">
    <router-view></router-view>
    <customMenu></customMenu>
  </div>
</template>

<script>
import customMenu from '@/components/Menu'

export default {
  name: 'app',
  components: { customMenu }
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

@font-face {
    font-family: 'jaap-regular';
    src: url('./assets/fonts/regular/jaapokki-regular.eot'),
         url('./assets/fonts/regular/jaapokki-regular.woff') format('woff'),
         url('./assets/fonts/regular/jaapokki-regular.ttf') format('truetype'),
         url('./assets/fonts/regular/jaapokki-regular.svg') format('svg');
    font-weight: normal;
    font-style: normal;
}

@font-face {
    font-family: 'jaap-substract';
    src: url('./assets/fonts/substract/jaapokki-substract.eot'),
         url('./assets/fonts/substract/jaapokki-substract.woff') format('woff'),
         url('./assets/fonts/substract/jaapokki-substract.ttf') format('truetype'),
         url('./assets/fonts/substract/jaapokki-substract.svg') format('svg');
    font-weight: normal;
    font-style: normal;
}
/*TODO: Change the word 'text to 'font'*/
.regular-text {
  font-family: 'jaap-regular';
}

.substracted-text {
  font-family: 'jaap-substract';
}

</style>
