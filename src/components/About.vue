<template lang="html">
  <section id="aboutComponent" class="fill-height">
    <mobileNav></mobileNav>
    <aside class="col-sm-12 col-md-4 profile-pic-container fill-height">
        <figure class="profile-pic fill-height"></figure>
    </aside>
    <aside class="col-sm-12 col-md-8 description-container fill-height scroll-content">
      <h1 class="section-title about-title">{{title}}</h1>
      <div class="row fill-height">
        <div class="col-sm-12 col-md-10">
          <p class="section-regular-text">I am a <span class="section-highlighted-text">UX designer</span> and a <span class="section-highlighted-text">front-end developer</span> with +5 years of development
          experience in different projects and areas from advertising sites to web
          applications. My commitment to team progress has been recurrently praised
          throught my different job positions, along with my communication
          abilities <span class="section-highlighted-text section-highlighted-italic-text">(both spanish and english)</span> and business envisioning for every project.
          </p>
          <p class="section-regular-text">
             Lorem ipsum dolor sit amet, consectetur adipiscing elit. Etiam sit amet augue massa.
             Nam sed volutpat urna. Vivamus consequat cursus velit eget dictum. Proin suscipit tincidunt dolor,
             eget consectetur lectus iaculis sit amet. Sed suscipit et velit condimentum pellentesque.
             Sed vulputate nisl vitae mauris viverra lobortis. Sed vel nisi nisi. Nunc sodales non lacus vitae hendrerit.
             Aenean consectetur accumsan lectus vitae blandit. Curabitur tincidunt vestibulum odio quis malesuada.
          </p>
          <!-- TODO: TEXT FOR ABOUT SHOULD BE MODIFIED -->
          <div class="row panels-container">
            <faPanel title="companies" v-bind:elements="panelData.companies"></faPanel>
            <faPanel title="technologies" v-bind:elements="panelData.tools"></faPanel>
          </div>
        </div>
      </div>

    </aside>
  </section>
</template>

<script>
import faPanel from '@/components/fa-panel/fa-panel'
import mobileNav from '@/components/fa-mobile-nav/fa-mobile-nav'

export default {
  name: 'About',
  data() {
    return {
      title: 'A B O U T',
      panelData: {
        companies: [
          { name : 'Velocity Partners', src: 'company-001.png'},
          { name : 'Eafit', src: 'company-002.png'},
          { name : 'DDB', src: 'company-003.png'},
          { name : 'eHarmony', src: 'company-004.png'},
          { name : 'SignalPath', src: 'company-005.png'}
        ],
        tools: [
          { name : 'NG', src: 'tech-001.png'},
          { name : 'Sass', src: 'tech-002.png'},
          { name : 'vue', src: 'tech-003.png'},
          { name : 'stylus', src: 'tech-004.png'},
          { name : 'bootstrap', src: 'tech-005.png'},
          { name : 'gulp', src: 'tech-006.png'},
          { name : 'webpack', src: 'tech-007.png'},
          { name : 'typescript', src: 'tech-008.png'}
        ]
      }
    }
  },
  components: { faPanel, mobileNav }
}
</script>

<style lang="css">
  /*Profile picture*/
  #aboutComponent .about-title{
    text-align: left;
    padding-left: 50px;
    padding-bottom: 50px;
  }

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
  /*Description container*/
  #aboutComponent .panels-container{
    padding-top: 50px;
  }

  /* Small Devices, Tablets */
  @media only screen and (max-width : 768px) {
    #aboutComponent .profile-pic-container .profile-pic{
      height: 300px;
      background-position: auto center;
    }
    #aboutComponent .about-title{
      text-align: center;
      font-size: 3.6em;
      padding: 30px 0 30px 0;
    }
  }
</style>
