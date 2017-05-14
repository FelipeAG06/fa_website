<template lang="html">
  <div id="faPanel" class="col-sm-12 col-md-6">
    <div class="panel custom-fa-panel">
      <div class="panel-heading custom-fa-panel-heading">
        <h4 class="panel-title regular-font">{{title}}</h4>
      </div>
      <!-- Panels -->
      <div class="panel-body custom-fa-panel-body">
        <ul class="list-inline row">
          <li v-for="element in elements" class="col-sm-8 col-md-4">
              <img v-bind:src="urlParse(element.src)" v-bind:alt="element.name">
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
  methods: {
    uppercaseFilter: function(text) {
      return text.toUppercase();
    },
    urlParse: function(path) {
      return images('./' + path)
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
</style>
