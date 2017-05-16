<template lang="html">
  <div id="faPanel" class="col-sm-12 col-md-6">
    <div class="panel custom-fa-panel">
      <div class="panel-heading custom-fa-panel-heading">
        <h4 class="panel-title regular-font">{{title}}</h4>
      </div>
      <!-- Panels -->
      <div class="panel-body custom-fa-panel-body">
        <ul v-for="pageItems in pages">
          <li v-for="item in pageItems" class="custom-fa-panel-items">
              <img v-bind:src="urlParse(item.src)" v-bind:alt="item.name">
          </li>
        </ul>
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
    this.setPages();
  },
  methods: {
    uppercaseFilter: function(text) {
      return text.toUppercase();
    },
    urlParse: function(path) {
      return images('./' + path)
    },
    setPages: function() {
      if(this.elements.length > 3) {
        this.pages = _.chunk(this.elements, 3);
      }
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

#faPanel .custom-fa-panel .custom-fa-panel-body ul{
  width: inherit;
  height: 100%;
  display: inline-block;
  padding: 0;
  list-style: none;
}

#faPanel .custom-fa-panel .custom-fa-panel-body ul:nth-child(2){
  display: none;
}

#faPanel .custom-fa-panel .custom-fa-panel-items{
  width: 33%;
  height: auto;
  float: left;
  padding: 15px;
}
</style>
