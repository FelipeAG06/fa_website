<template lang="html">
  <section id="contactComponent" class="fill-height">
    <mobileNav></mobileNav>
    <div class="row fill-height">
      <section class="col-sm-12 form-section">
        <h1 class="section-title text-center">{{title}}</h1>
        <section class="container">
          <p class="section-regular-text text-center">
             Revolutionary, fun and challenging projects are my favorites. If you have something to talk about or share please feel free to <span class="section-highlighted-text section-highlighted-italic-text">Get in touch!</span>
          </p>
          <div class="col-sm-12 col-md-6 col-centered custom-form">
            <form action="https://formspree.io/felipeag06@gmail.com" method="POST">
              <!-- Name -->
              <div class="form-group">
                <label for="nameField" class="fa-form-label">Name</label>
                <input id="nameField" type="name" name="user_name" class="fa-form-control" aria-describedby="emailHelp" placeholder="Your name" required>
              </div>
              <!-- Subject -->
              <div class="form-group">
                <label for="subjectField" class="fa-form-label">Subject</label>
                <input id="subjectField" type="subject" name="subject" class="fa-form-control" aria-describedby="e mailHelp" placeholder="Subject" required>
              </div>
              <!-- Message -->
              <div class="form-group">
                <label for="messageField" class="fa-form-label">Message</label>
                <textarea id="messageField" name="message" class="fa-form-control" rows="3" cols="80" placeholder="Your message" required></textarea>
              </div>
              <div class="fa-contact-container">
                <input type="submit" class="btn fa-contact-button" value="S E N D"/>
              </div>
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
    <customMenu class="hidden-sm hidden-md hidden-xs"></customMenu>
  </section>
</template>

<script>
  import socialLinks from '@/components/Social-links'
  import mobileNav from '@/components/fa-mobile-nav/fa-mobile-nav'
  import customMenu from '@/components/Menu'

  export default {
    name:'Contact',
    data() {
      return {
        title: 'C O N T A C T'
      }
    },
    mounted() {
      let title = $('.section-title');
      let paragraph = $('.section-regular-text');
      let form = $('.custom-form');
      let picture = $('.contact-picture-container');

      TweenMax.fromTo(title, 1, {opacity:0, x: 80}, {opacity:1, x:0});
      TweenMax.fromTo(paragraph, 1, {opacity:0}, {opacity:1, delay:0.2});
      TweenMax.fromTo(form, 1, {opacity:0, x: -80}, {opacity:1, x:0});
      TweenMax.fromTo(picture, 1, {opacity:0}, {opacity:1, delay:0.2});
    },
    components: { socialLinks, mobileNav, customMenu }
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

#contactComponent .fa-form-label {
  font-family: 'Roboto';
  color: #442CAC;
}

#contactComponent .fa-contact-container {
  display: flex;
  justify-content: center;
}

#contactComponent .fa-contact-container .fa-contact-button {
  background: #442CAC;
  color: white;
  border-radius: 0;
  width: 25%;
  font-family: 'Roboto';
  opacity: 1;
  transition: all 0.3s cubic-bezier(.25,.8,.25,1);
}

#contactComponent .fa-contact-container .fa-contact-button:hover {
  background: #442CAC;
  color: #00FFA3;
  box-shadow: 0 8px 7px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
  transition: all 0.3s cubic-bezier(.25,.8,.25,1);
}

#contactComponent .fa-form-control {
    display: block;
    width: 100% !important;
    height: 34px;
    font-size: 14px;
    line-height: 1.42857143;
    color: #555;
    background-color: #fff;
    background-image: none;
    transition: border-color ease-in-out .15s;
    border: none;
    border-bottom: solid 1px #ccc;
}

#contactComponent .fa-form-control:focus{
  border-bottom: solid 1px #442CAC;
  outline: 0;
  outline: none;
}

#contactComponent .contact-picture-container .contact-picture{
  height: 100%;
  background-image: url('../assets/img/contact/contact-city-temp.png');
  background-size: cover;
  background-position: center center;
}
/* Small Devices, Tablets */
@media only screen and (max-width : 768px) {
  #contactComponent .section-title{
    font-size: 3.6em;
  }

  #contactComponent .fa-contact-container .fa-contact-button {
    background: #442CAC;
    color: white;
    border-radius: 0;
    width: 100%;
    font-family: 'Roboto';
    opacity: 1;
    transition: all 0.3s cubic-bezier(.25,.8,.25,1);
}

  #contactComponent .form-section {
    padding-top: 80px;
  }

  /*Picture section*/
  #contactComponent .contact-picture-container {
    height: 250px;
    margin-top: 50px;
  }

}
</style>
