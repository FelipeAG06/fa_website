<template lang="html">
  <div id="faPanel" class="col-sm-12 col-md-6">
    <div class="panel custom-fa-panel">
      <div class="panel-heading custom-fa-panel-heading">
        <h4 class="panel-title regular-font">{{title}}</h4>
      </div>
      <div class="panel-body custom-fa-panel-body">
        <ul class="list-inline row">
          <li class="col-sm-4">
              item 1
          </li>
          <li class="col-sm-4">
              item 2
          </li>
          <li class="col-sm-4">
              item 3
          </li>
        </ul>
        <ul class="list-inline row hidden">
          <li class="col-sm-4">
              item 4
          </li>
          <li class="col-sm-4">
              item 5
          </li>
          <li class="col-sm-4">
              item 6
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'faPanel',
  props: ['title'],
  methods: {
    uppercaseFilter: function(text) {
      return text.toUppercase();
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
