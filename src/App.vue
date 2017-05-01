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

<style lang="css">
.container-mask {
  padding: 0 !important;
  overflow: hidden;
}

.col-centered{
    float: none;
    margin: 0 auto;
}

/*Text classes*/
.section-title {
  font-family: 'jaap-regular';
  color: #442CAC;
  font-size: 7em;
}

.section-regular-text {
  font-family: 'Roboto';
  font-size: 1.2em;
}

.section-highlighted-text {
  font-family: 'Roboto';
  color: #00FFA3;
  font-weight: bold;
  font-size: 1em;
}

.section-highlighted-italic-text {
  font-family: 'Roboto';
  font-style: italic;
}

/*Custom Font faces*/
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

.regular-font {
  font-family: 'jaap-regular';
}

.substracted-font {
  font-family: 'jaap-substract';
}

/*Reusable classes*/
.fill-height{
  min-height: 100%;
  height: 100%;
}


/* Small Devices, Tablets */
@media only screen and (max-width : 768px) {
  .fill-height{
    min-height: 100%;
    height: auto;
  }
}


</style>
