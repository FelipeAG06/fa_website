<template lang="html">
  <div id="mobileNav" class="mobile-nav-container hidden-lg" v-bind:class="{'menu-closed': isClosed, 'menu-opened': isOpen}">
    <nav class="icon-wrapper">
      <aside class="col-sm-6 pull-right">
        <a href="#" class="menu-link" v-on:click="menuToggle">
          <i class="mdi menu-icon" v-bind:class="{'mdi-menu': isClosed, 'mdi-close': isOpen}"></i>
        </a>
      </aside>
    </nav>

    <div class="mobile-popup-container">
      <nav class="mobile-popup">
        <ul>
          <li>
            <router-link v-bind:to="'/'">
              <h2 class="regular-font text-center">Home</h2>
            </router-link>
          </li>
          <li>
            <router-link v-bind:to="'/about'">
              <h2 class="regular-font text-center">About</h2>
            </router-link>
          </li>
          <li>
            <router-link v-bind:to="'/contact'">
              <h2 class="regular-font text-center">Contact</h2>
            </router-link>
          </li>
        </ul>
      </nav>
    </div>
  </div>
</template>

<script>
import customMenu from '@/components/Menu'
export default {
  name:'mobileNav',
  components: { customMenu },
  data() {
    return {
      isClosed: true,
      isOpen: false
    }
  },
  methods: {
    menuToggle: function() {
      // TODO: This needs refactor! Time quick solution was made
      if(!this.isClosed) {
        this.isClosed = true;
        this.isOpen = false;

        return;
      }
      this.isClosed = false;
      this.isOpen = true;
    }
  }
}
</script>

<style lang="css">
  #mobileNav.mobile-nav-container {
    width: 100%;
    height: 100%;
    position: fixed;
    top: 0;
    padding-top: 15px;
    z-index: 9999;
  }

  #mobileNav .icon-wrapper {
    position: fixed;
    width: 100%;
    z-index: 999;
    padding-right: 15px;
  }

  #mobileNav .icon-wrapper aside{
    background: rgba(1, 1, 1, 0.5) !important;
  }

  #mobileNav .menu-link {
    width: 100%;
    height: 100%;
    display: inline-block;
  }

  #mobileNav .menu-link .menu-icon {
    font-size: 2em;
    color: #00FFA3;
  }

  /*Pop up Menu*/

  #mobileNav .mobile-popup-container {
    min-height: 100%;
    height: 100%;
    position: fixed;
    width: 100%;
    top: 0;
  }

  #mobileNav .mobile-popup-container .mobile-popup {
    padding-top: 100px;
  }

  #mobileNav .mobile-popup-container .mobile-popup ul{
      list-style: none;
      padding: 0;
  }

  #mobileNav .mobile-popup-container .mobile-popup ul li {
    padding: 2em 0;
  }

  #mobileNav .mobile-popup-container .mobile-popup ul li h2{
    color: #fff;
    font-size: 4em;
  }

  /*Utility classes*/
  .menu-closed {
      background: none !important;
  }

  .menu-closed > .mobile-popup-container{
    display: none;
  }

  .menu-opened {
      background: rgba(1, 1, 1, 0.8) !important;
  }

  .menu-opened > .mobile-popup-container{
    display: auto;
  }

  .selected-link{
    color:#00FFA3;
  }
</style>
