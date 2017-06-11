<template lang="html">
  <div id="faPanel" class="col-sm-12 col-md-6" v-bind:data="title">
    <div class="panel custom-fa-panel">
      <div class="panel-heading custom-fa-panel-heading">
        <h4 class="panel-title regular-font">{{title}}</h4>
      </div>
      <!-- Panels -->
      <div class="panel-body custom-fa-panel-body">
        <ul v-for="(pageItems, index) in pages" v-bind:class="{'current-page': index == 0 }">
          <li v-for="item in pageItems" class="custom-fa-panel-items">
              <img v-bind:src="urlParse(item.src)" v-bind:alt="item.name">
          </li>
        </ul>
      </div>
      <div class="slide-buttons-container">
        <div class="pull-right slide-buttons">
          <a class="col-sm-2 col-md-4 btn-elem" v-for="(page, index) in pages" v-on:click="goToPage(index)">
            <i class="mdi mdi-icon mdi-circle"></i>
          </a>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
var images = require.context('@/assets/img/about/panels', false,  /\.png$/)
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
  created() {
    this.setupPages();
  },
  methods: {
    uppercaseFilter: function(text) {
      return text.toUppercase();
    },
    urlParse: function(path) {
      return images('./' + path)
    },
    setupPages: function() {
      if(this.elements.length > 3) {
        this.pages = _.chunk(this.elements, 3);
      }

    },
    goToPage: function(idx) {
      const CURRENT_PAGE_CLASS = 'current-page';
      let page = $("#faPanel[data='"+ this.title + "'] .custom-fa-panel-body ul");
      let buttons = $("#faPanel[data='"+ this.title + "'] .slide-buttons-container .slide-buttons a");
      console.log(page);
      page
        .eq(idx)
        .addClass(CURRENT_PAGE_CLASS)
        .siblings()
        .removeClass(CURRENT_PAGE_CLASS);

      buttons
        .eq(idx)
        .find('a')
        .focus();
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

#faPanel[data*=companies] .custom-fa-panel .custom-fa-panel-body ul{
  width: inherit;
  height: 100%;
  display: inline-block;
  padding: 0;
  list-style: none;
  opacity: 0;
  display: none;
  transition: all 2s ease-in;
}

#faPanel[data*=technologies] .custom-fa-panel .custom-fa-panel-body ul{
  width: inherit;
  height: 100%;
  display: inline-block;
  padding: 0;
  list-style: none;
  opacity: 0;
  display: none;
  transition: all 2s ease-in;
}

#faPanel[data*=companies] .custom-fa-panel .custom-fa-panel-body ul.current-page {
  display: block;
  opacity: 1;
  transition: all 2s ease-in;
}

#faPanel[data*=technologies] .custom-fa-panel .custom-fa-panel-body ul.current-page {
  display: block;
  opacity: 1;
  transition: all 2s ease-in;
}

#faPanel[data*=companies] .custom-fa-panel .slide-buttons-container {
  background-color: #f7f7f7;
  height: 37px;
}

#faPanel[data*=technologies] .custom-fa-panel .slide-buttons-container {
  background-color: #f7f7f7;
  height: 37px;
}

#faPanel[data*="companies"] .custom-fa-panel .slide-buttons-container a:focus , a:hover{
  color:#442CAC;
  cursor: pointer;
}

#faPanel[data*="technologies"] .custom-fa-panel .slide-buttons-container a:focus , a:hover{
  color:#442CAC;
  cursor: pointer;
}

#faPanel .pagination-btn-container .btn-elem{
  display: inline-block;
}

#faPanel .custom-fa-panel .custom-fa-panel-items{
  width: 33%;
  height: auto;
  float: left;
  padding: 15px;
}
</style>
