<template lang="html">
  <nav id="socialLinks">
    <ul>
      <li>
        <a href="https://github.com/FelipeAG06" target="_blank">
          <i class="mdi mdi-github-face social-link-icon"></i>
        </a>
      </li>
      <li>
        <a href="https://www.behance.net/FelipeAlvarez" target="_blank">
          <i class="mdi mdi-behance social-link-icon"></i>
        </a>
      </li>
      <li>
        <a href="https://www.linkedin.com/in/felipe-alvarez-025724ab/" target="_blank">
          <i class="mdi mdi-linkedin social-link-icon"></i>
        </a>
      </li>
    </ul>
  </nav>
</template>

<script>
  export default {
    name:'socialLinks',
    mounted() {
      let socialNav = $('#socialLinks');
      TweenMax.fromTo(socialNav, 1, {opacity:0, y: 30}, {opacity:1, y: 0, delay:0.2});
    }
  }
</script>

<style lang="css">
  #socialLinks {
    width: auto;
    height: 50px;
    position: fixed;
    bottom: 0;
    z-index: 998;
  }

  #socialLinks ul {
    list-style: none;
    padding: 0;
  }

  #socialLinks ul li {
    display: inline-block;
    width: 30px;
    height: 30px;
    background-color: #FFF;
    border-radius: 100%;
    margin: 0 20px;
  }

  #socialLinks ul li a {
    width: inherit;
    height: inherit;
    display: inline-block;
  }

  #socialLinks ul li a .social-link-icon {
    font-size: 1.5em;
    color: #442CAC;
    width: inherit;
    height: inherit;
    display: inline-block;
    text-align: center;
    transition: all 0.3s cubic-bezier(.25,.8,.25,1);
  }
  
  #socialLinks ul li a:hover .social-link-icon {
    font-size: 1.5em;
    color: #442CAC;
    width: inherit;
    height: inherit;
    display: inline-block;
    text-align: center;
    transform: rotate(-20deg);
    transition: all 0.3s cubic-bezier(.25,.8,.25,1);
  }
  
</style>
