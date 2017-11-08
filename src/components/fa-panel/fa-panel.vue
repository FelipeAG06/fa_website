<template lang="html">
  <div id="faPanel" class="col-sm-12 col-md-6" v-bind:data="title">
    <div class="panel custom-fa-panel">
      <div class="panel-heading custom-fa-panel-heading">
        <h4 class="panel-title regular-font">{{title}}</h4>
      </div>
      <!-- Panels -->
      <div class="panel-body custom-fa-panel-body">
        <ul class="page-items-container"
            v-for="(pageItems, index) in pages"
            v-bind:id="title + '-page-' + index" 
            v-bind:class="{'current-page': index == 0 }">
          <li v-for="item in pageItems" class="custom-fa-panel-items">
              <img v-bind:src="urlParse(item.src)" v-bind:alt="item.name">
          </li>
        </ul>
      </div>
      <div class="slide-buttons-container">
        <div class="slide-buttons">
          <a class="btn-elem fa-panel-button"
             v-bind:id="title +'-'+ index"
             v-bind:class="{'selected-panel-button': index === 0}"
             v-for="(page, index) in pages"
             v-on:click="goToPage(index)"></a>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
var images = require.context('@/assets/img/about/panels', false,  /\.png$/);
export default {
  name: 'faPanel',
  props: {
    title:{
      type: String,
      required: true
    },
    elements: {
      type: Array,
      required:true
    }
  },
  data() {
    return {
        pages: null
    }
  },
  mounted() {
    let panel = $('.custom-fa-panel');
    TweenMax.fromTo(panel, 1, {opacity:0}, {opacity:1, delay: 0.5});
    this.goToPage(0);
  },
  created() {
    this.setupPages();
  },
  methods: {
    uppercaseFilter: function(text) {
      return text.toUppercase();
    },
    urlParse: function(path) {
      return images('./' + path);
    },
    setupPages: function() {
      if(this.elements.length > 3) {
        this.pages = _.chunk(this.elements, 3);
      }

    },
    goToPage: function(idx) {
      const CURRENT_PAGE_CLASS = 'current-page';
      let page = $('#' + this.title + '-page-' + idx);
      let buttons = $("#faPanel[data='"+ this.title + "'] .slide-buttons-container .slide-buttons a");
      let selectedItem = $('#' + this.title + '-' + idx);

      //Set new Page
      page
        .addClass(CURRENT_PAGE_CLASS)
        .siblings()
        .removeClass(CURRENT_PAGE_CLASS)

      TweenMax.fromTo(page, 0.5, {x: 25, opacity:0}, {x: 0, opacity:1});

      //Set button state
      selectedItem
        .addClass('selected-panel-button')
        .siblings()
        .removeClass('selected-panel-button');
    }
  }
}
</script>

<style lang="css">
/*Custom panel*/
#faPanel .custom-fa-panel {
  border: none;
}

.panel-title{
  text-transform: uppercase;
  color: #442CAC;
  letter-spacing: 3px;
  font-size: 1.2em;
  text-align: center;
}

#faPanel .custom-fa-panel .custom-fa-panel-heading {
  background-color: #00fea3;
}

#faPanel .custom-fa-panel .custom-fa-panel-body {
  background-color: #f7f7f7;
}

#faPanel .custom-fa-panel .custom-fa-panel-body .page-items-container {
  display: flex;
  justify-content: space-between;
}

#faPanel[data*=companies] .custom-fa-panel .custom-fa-panel-body ul{
  width: inherit;
  height: 100%;
  display: inline-block;
  padding: 0;
  list-style: none;
  opacity: 0;
  display: none;
}

#faPanel[data*=technologies] .custom-fa-panel .custom-fa-panel-body ul{
  width: inherit;
  height: 100%;
  display: flex;
  justify-content: center;
  padding: 0;
  list-style: none;
  opacity: 0;
  display: none;
}

#faPanel[data*=companies] .custom-fa-panel .custom-fa-panel-body ul.current-page {
  display: flex;
  justify-content: space-between;
}

#faPanel[data*=technologies] .custom-fa-panel .custom-fa-panel-body ul.current-page {
  display: flex;
  justify-content: space-between;
}

#faPanel[data*=companies] .custom-fa-panel .slide-buttons-container {
  background-color: #f7f7f7;
  height: 25px;
  display: flex;
  justify-content: center;
}

#faPanel[data*=technologies] .custom-fa-panel .slide-buttons-container {
  background-color: #f7f7f7;
  height: 25px;
  display: flex;
  justify-content: center;
}

#faPanel[data*=companies] .custom-fa-panel .slide-buttons .fa-panel-button{
    width: 15px;
    height: 15px;
    background-color: #ccc;
    border-radius: 100%;
    display: inline-block;
    margin: 0 10px;
}

#faPanel[data*=technologies] .custom-fa-panel .slide-buttons .fa-panel-button{
    width: 15px;
    height: 15px;
    background-color: #ccc;
    border-radius: 100%;
    display: inline-block;
    margin: 0 10px;
}

#faPanel[data*="companies"] .custom-fa-panel .slide-buttons-container a:hover{
  cursor: pointer;
  box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
  transition: all 0.3s cubic-bezier(.25,.8,.25,1);
}

#faPanel[data*="technologies"] .custom-fa-panel .slide-buttons-container a:hover{
  cursor: pointer;
  box-shadow: 0 6px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
  transition: all 0.3s cubic-bezier(.25,.8,.25,1);
}

#faPanel[data*="technologies"] .custom-fa-panel .slide-buttons-container .selected-panel-button{
  background-color: #00fea3;
  cursor: pointer;
}

#faPanel[data*="companies"] .custom-fa-panel .slide-buttons-container .selected-panel-button{
  background-color: #00fea3;
  cursor: pointer;
}

#faPanel .pagination-btn-container .btn-elem{
  display: inline-block;
}
</style>
