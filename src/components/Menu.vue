<template lang="html">
  <div id="custom-menu" class="fill-height">
    <ul>
      <li class="regular-text">
        <router-link v-bind:to="'/'">Home</router-link>
      </li>
      <li class="regular-text">
        <router-link v-bind:to="'/about'">About</router-link>
      </li>
      <li class="regular-text">Work</li>
      <li class="regular-text">Contact</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'customMenu',
  inherit: true
}
</script>

<style lang="css">
  #custom-menu {
    position: fixed;
    display: flex;
    align-items: center;
    top: 0;
    right: 0;
  }

  #custom-menu ul {
    list-style: none;
    padding-right: 30px;
  }
  #custom-menu ul li,a{
    height: 50px;
    color: #00FFA3;
    font-size: 20px;
  }

  #custom-menu ul li a:hover{
    height: 50px;
    color: #CCC;
  }
</style>
