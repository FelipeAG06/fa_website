<template lang="html">
  <section id="contactComponent" class="fill-height">
    <div class="row fill-height">
      <section class="col-sm-12 form-section">
        <h1 class="section-title text-center">{{title}}</h1>
        <section class="container">
          <p class="section-regular-text text-center">
             Revolutionary, fun and challenging projects are my favorites. If you have something to talk about or share please feel free to <span class="section-highlighted-text section-highlighted-italic-text">Get in touch!</span>
          </p>
          <div class="col-sm-12 col-md-6 col-centered">
            <form>
              <!-- Name -->
              <div class="form-group">
                <label for="exampleInputEmail1">Name</label>
                <input type="name" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Your name" required>
              </div>
              <!-- Subject -->
              <div class="form-group">
                <label for="exampleInputEmail1">Subject</label>
                <input type="subject" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Subject" required>
              </div>
              <!-- Message -->
              <div class="form-group">
                <label for="exampleInputEmail1">Message</label>
                <textarea name="message" class="form-control" rows="3" cols="80" placeholder="Your message" required></textarea>
              </div>
              <button type="button" class="btn btn-secondary"> S E N D</button>
            </form>
          </div>
        </section>
      </section>
      <section class="col-sm-12 contact-picture-container">
        <figure class="contact-picture"></figure>
        <div class="social-links-wrapper">
          <socialLinks></socialLinks>
        </div>
      </section>
    </div>
  </section>
</template>

<script>
  import socialLinks from '@/components/Social-links'
  export default {
    name:'Contact',
    data() {
      return {
        title: 'C O N T A C T'
      }
    },
    components: { socialLinks }
  }
</script>

<style lang="css">
/*Form section*/
#contactComponent .form-section {
  height: 80%;
}

#contactComponent .form-section .form-section {
 padding: 0 100px !important;
}

/*Picture section*/
#contactComponent .contact-picture-container {
  height: 20%;
}

#contactComponent .contact-picture-container .contact-picture{
  height: 100%;
  background-image: url('../assets/img/contact/contact-city-temp.png');
  background-size: cover;
  background-position: center center;
}

</style>
