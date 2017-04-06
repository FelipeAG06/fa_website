<template lang="html">
  <div class="home-elements fill-height bg-transition">
    <div class="row">
      <div class="col-sm-12">
        <h1 class="text-center home-text t-name">Felipe Alvarez</h1>
        <h3 class="text-center home-text t-description">UX designer and Frontend developer</h3>
      </div>


    </div>

  </div>
</template>

<script>
export default {
  name: 'Home'
}
</script>

<style lang="css">
.home-text {
  color:#FFF;
}
.home-elements {
  background: white;
}
.bg-transition{
  /* Permalink - use to edit and share this gradient: http://colorzilla.com/gradient-editor/#01359f+0,7f24b7+88,7f24b7+100 */
  background: #01359f; /* Old browsers */
  background: -moz-linear-gradient(45deg,  #01359f 0%, #7f24b7 88%, #7f24b7 100%); /* FF3.6-15 */
  background: -webkit-linear-gradient(45deg,  #01359f 0%,#7f24b7 88%,#7f24b7 100%); /* Chrome10-25,Safari5.1-6 */
  background: linear-gradient(45deg,  #01359f 0%,#7f24b7 88%,#7f24b7 100%); /* W3C, IE10+, FF16+, Chrome26+, Opera12+, Safari7+ */
  filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#01359f', endColorstr='#7f24b7',GradientType=1 ); /* IE6-9 fallback on horizontal gradient */
}
</style>
