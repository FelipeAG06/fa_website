<template lang="html">
  <section id="aboutComponent" class="fill-height">
    <aside class="col-sm-12 col-md-4 profile-pic-container fill-height">
        <figure class="profile-pic fill-height"></figure>
    </aside>
    <aside class="col-sm-12 col-md-8 description-container fill-height">
      <h1 class="section-title">{{title}}</h1>
      <div class="row fill-height">
        <div class="col-sm-12 col-md-10">
          <p class="section-regular-text">I am a <span class="section-highlighted-text">UX designer</span> and a <span class="section-highlighted-text">front-end developer</span> with +5 years of development
          experience in different projects and areas from advertising sites to web
          applications. My commitment to team progress has been recurrently praised
          throught my different job positions, along with my communication
          abilities <span class="section-highlighted-text section-highlighted-italic-text">(both spanish and english)</span> and business envisioning for every project.
          </p>
          <!-- TODO: TEXT FOR ABOUT SHOULD BE MODIFIED -->
          <hr/>
          <div class="col-sm-12">
            <ul>
              <li>Some people I worked with</li>
              <li>Usage of Frontend technologies</li>
            </ul>
            <div class="companies-images">
              <!-- velocity -->
              <!-- Premera -->
              <!-- Eafit -->
              <!-- DDB -->
              <!-- eHarmony -->
              <!-- SignalPath -->

            </div>
            <div class="techs-images">
              <!-- Angular -->
              <!-- Vue -->
              <!-- Sass -->
              <!-- Gulp -->
              <!-- Webpack -->
              <!-- Less -->
              <!-- Typescript -->
            </div>
          </div>
        </div>
      </div>

    </aside>
  </section>
</template>

<script>
import faTabs from '@/components/fa-tabs/fa-tabs'
import faTabItem from '@/components/fa-tabs/fa-tab-item'

export default {
  name: 'About',
  data() {
    return {
      title: 'A B O U T'
    }
  },
  components: { faTabs, faTabItem }
}
</script>

<style lang="css">
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

</style>
