<template lang="html">
  <div id="homeComponent" class="fill-height home-elements-container bg-pattern bg-transition">
    <mobileNav></mobileNav>
    
    <div class="title-container">
      <div class="title">
        <h1 class="text-center home-text-color home-text-name substracted-font">{{nameTitle}} <span class="hidden-sm hidden-xs"> - </span> <br class="hidden-lg hidden-md">{{lastnameTitle}}</h1>
        <h3 class="text-center home-text-color home-text-description regular-font">{{descriptionTitle}}</h3>
      </div>
    </div>
    <socialLinks></socialLinks>
    <customPattern></customPattern>
    <customMenu class="hidden-sm hidden-xs"></customMenu>
  </div>
</template>

<script>
  import socialLinks from '@/components/Social-links'
  import mobileNav from '@/components/fa-mobile-nav/fa-mobile-nav'
  import customPattern from '@/components/fa-pattern/fa-pattern'
  import customMenu from '@/components/Menu'

  export default {
    name: 'Home',
    data () {
      return {
        nameTitle: 'F E L I P E',
        lastnameTitle:'A L V A R E Z',
        descriptionTitle: 'Frontend developer and Design enthusiast'
      }
    },
    mounted() {
      let nameText = $('.home-text-name');
      let descriptionText = $('.home-text-description');

      TweenMax.fromTo(nameText, 1, {opacity:0, y: -20}, {opacity:1, y: 0, delay:0.2});
      TweenMax.fromTo(descriptionText, 1, {opacity:0}, {opacity:1, delay:0.5});
    },
    components: { socialLinks, mobileNav, customPattern, customMenu }
  }
</script>

<style lang="css">
  .home-text-color {
    color:#FFF;
  }
  
  .title-container {
    z-index: 997;
  }

  .home-text-name {
    font-size: 4em;
  }

  .home-text-description {
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
    /* background: url('../assets/img/home/pattern.png') no-repeat, linear-gradient(45deg,  #01359f 0%,#7f24b7 88%,#7f24b7 100%);  W3C, IE10+, FF16+, Chrome26+, Opera12+, Safari7+  */
    filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#01359f', endColorstr='#7f24b7',GradientType=1 ); /* IE6-9 fallback on horizontal gradient */
  }

  /* Small Devices, Tablets */
  @media only screen and (max-width : 768px) {
    .home-elements-container{
      width: 100%;
      height: 100%;
      position: fixed;
    }
    .home-text-name {
      font-size: 3em;
    }

    .home-text-description {
      font-size: 1.3em;
    }
  }
</style>
