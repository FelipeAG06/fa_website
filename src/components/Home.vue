<template lang="html">
  <div class="fill-height home-elements-container bg-pattern bg-transition">
    <div class="title-container">
      <div class="title">
        <h1 class="text-center home-text t-name substracted-font">{{nameTitle}}</h1>
        <h3 class="text-center home-text t-description regular-font">{{descriptionTitle}}</h3>
      </div>
    </div>

  </div>
</template>

<script>
  export default {
    name: 'Home',
    data () {
      return {
        nameTitle: 'F E L I P E   A L V A R E Z',
        descriptionTitle: 'UX designer and Frontend developer'
      }
    }
  }
</script>

<style lang="css">
  .home-text {
    color:#FFF;
  }

  .t-name {
    font-size: 4em;
  }

  .t-description {
    font-size: 2em;
  }

  .home-elements-container{
    height: 100%;
    display: -ms-flexbox;
    display: -webkit-flex;
    display: flex;
    -ms-flex-align: center;
    -webkit-align-items: center;
    -webkit-box-align: center;
    align-items: center;
    justify-content: center;
  }

  .bg-transition {
    /* Permalink - use to edit and share this gradient: http://colorzilla.com/gradient-editor/#01359f+0,7f24b7+88,7f24b7+100 */
    background: #01359f; /* Old browsers */
    background: -moz-linear-gradient(45deg,  #01359f 0%, #7f24b7 88%, #7f24b7 100%); /* FF3.6-15 */
    background: -webkit-linear-gradient(45deg,  #01359f 0%,#7f24b7 88%,#7f24b7 100%); /* Chrome10-25,Safari5.1-6 */
    /*TODO: Pattern must be moved else where since it will be animated*/
    background: url('../assets/img/home/pattern.png') no-repeat, linear-gradient(45deg,  #01359f 0%,#7f24b7 88%,#7f24b7 100%); /* W3C, IE10+, FF16+, Chrome26+, Opera12+, Safari7+ */
    filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#01359f', endColorstr='#7f24b7',GradientType=1 ); /* IE6-9 fallback on horizontal gradient */
  }
</style>
