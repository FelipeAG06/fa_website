<template lang="html">
  <nav id="customMenu" class="fill-height">
    <ul>
      <li class="regular-font">
        <router-link v-bind:to="'/'">Home</router-link>
      </li>
      <li class="regular-font">
        <router-link v-bind:to="'/about'">About</router-link>
      </li>
      <!-- <li class="regular-font">Work</li> -->
      <li class="regular-font">
        <router-link v-bind:to="'/contact'">Contact</router-link>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'customMenu',
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
  }

  #customMenu ul {
    list-style: none;
    padding-right: 30px;
  }
  #customMenu ul li,a{
    height: 50px;
    color: #00FFA3;
    font-size: 20px;
  }

  #customMenu ul li a:hover{
    height: 50px;
    color: #CCC;
  }
</style>
