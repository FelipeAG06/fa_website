<template lang="html">
  <section id="aboutComponent" class="fill-height">
    <aside class="col-sm-12 col-md-4 profile-pic-container fill-height">
        <figure class="profile-pic fill-height"></figure>
    </aside>
    <aside class="col-sm-12 col-md-8 description-container fill-height">
      <h1 class="about-title">{{title}}</h1>
      <p>I am a UX designer and a front-end developer with +5 years of development
      experience in different projects and areas from advertising sites to web
      applications. My commitment to team progress has been recurrently praised
      throught my different job positions, along with my communication
      abilities (both spanish and english) and business envisioning for every project.
      </p>
    </aside>
  </section>
</template>

<script>
export default {
  name: 'About',
  data() {
    return {
      title: 'A B O U T'
    }
  }
}
</script>

<style lang="css">
  #aboutComponent .about-title {
   font-family: 'jaap-regular';
   font-size: 9em;
  }
  /*Profile picture*/
  #aboutComponent .profile-pic-container{
   height: 100%;
   background-color: #CCC;
   padding: 0px;
  }

  #aboutComponent .profile-pic-container .profile-pic{
   background-image: url('../assets/img/about/profile-temp.png');
   background-size: cover;
  }


  /*Description container*/
  #aboutComponent .description-container{
   /*background-color: #442CAC;*/
   background-color: #FFF;
  }

  #aboutComponent .description-container .about-title{
    color: #442CAC;
  }

</style>
