<template lang="html">
  <nav id="customMenu" class="fill-height">
    <ul>
      <li class="regular-font">
        <router-link v-bind:to="'/'" id="homePage" class="menu-link">Home</router-link>
      </li>
      <li class="regular-font">
        <router-link v-bind:to="'/about'" id="aboutPage" class="menu-link">About</router-link>
      </li>
      <li class="regular-font">
        <router-link v-bind:to="'/contact'" id="contactPage" class="menu-link">Contact</router-link>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'customMenu',
  data() {
    return {}
  },
  mounted() {
    let currentRoute = this.$route.name;

    switch (currentRoute) {
      case 'About':
        this.selectCurrentMenuItem('#aboutPage');
        break;
      case 'Contact':
        this.selectCurrentMenuItem('#contactPage');
        break;
      default:
        this.selectCurrentMenuItem('#homePage');
    }

  },
  methods: {
    selectCurrentMenuItem: function(element) {
      $(element)
          .addClass('current-page')
          .siblings()
          .removeClass('current-page');
      }
  },
  inherit: true
}
</script>

<style lang="css">
  #customMenu {
    position: fixed;
    display: flex;
    align-items: center;
    top: 0;
    right: 0;
    z-index: 999;
  }

  #customMenu ul {
    list-style: none;
    padding-right: 30px;
  }

  #customMenu ul li {
    width: 70px;
    height: 50px;
  }

  /* HOME LINKS STYLES */
  #homeComponent #customMenu ul li .menu-link{
    height: 50px;
    color: #00FFA3;
    font-size: 20px;
    transition: all 0.3s cubic-bezier(.25,.8,.25,1);
  }

  #homeComponent #customMenu ul li .menu-link:hover {
    height: 100px;
    color: white;
    transition: all 0.3s cubic-bezier(.25,.8,.25,1);
    text-decoration: none;
    border-bottom: solid 1px white;
    padding-right: 6px;
  }

  #homeComponent #customMenu ul li .current-page {
    height: 100px;
    color: white !important;
    border-bottom: solid 1px white;
    padding-right: 6px;
  }

  #homeComponent #customMenu ul li .menu-link:focus {
    color: white;
    text-decoration: none;
  }

  /* ABOUT LINKS STYLES */
  #aboutComponent #customMenu ul li .menu-link{
    height: 50px;
    color: #442CAC;
    font-size: 20px;
    transition: all 0.3s cubic-bezier(.25,.8,.25,1);
  }

  #aboutComponent #customMenu ul li .menu-link:hover{
    height: 100px;
    color: #442CAC !important;
    transition: all 0.3s cubic-bezier(.25,.8,.25,1);
    text-decoration: none;
    border-bottom: solid 1px #442CAC;
    padding-right: 6px;
  }

  #aboutComponent #customMenu ul li .menu-link:focus {
    color: #442CAC;
    text-decoration: none;
  }

  #aboutComponent #customMenu ul li .current-page{
    color: #442CAC !important;
    border-bottom: solid 1px #442CAC;
    padding-right: 6px;
  }

   /* CONTACT LINKS STYLES */
  #contactComponent #customMenu ul li .menu-link{
    height: 50px;
    color: #442CAC;
    font-size: 20px;
    transition: all 0.3s cubic-bezier(.25,.8,.25,1);
  }

  #contactComponent #customMenu ul li .menu-link:hover{
    height: 100px;
    color: #442CAC !important;
    transition: all 0.3s cubic-bezier(.25,.8,.25,1);
    text-decoration: none;
    border-bottom: solid 1px #442CAC;
    padding-right: 6px;
  }

  #contactComponent #customMenu ul li .menu-link:focus {
    color: #442CAC;
    text-decoration: none;
  }

  #contactComponent #customMenu ul li .current-page{
    color: #442CAC !important;
    border-bottom: solid 1px #442CAC;
    padding-right: 6px;
  }
</style>
