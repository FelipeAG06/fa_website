<template lang="html">
  <div id="faPanel" class="col-sm-12 col-md-6">
    <div class="panel custom-fa-panel">
      <div class="panel-heading custom-fa-panel-heading">
        <h4 class="panel-title regular-font">{{title}}</h4>
      </div>
      <!-- Companies -->
      <div class="panel-body custom-fa-panel-body" v-if="type === 'company'">
        <ul class="list-inline row">
          <li class="col-sm-8 col-md-4">
              <slot name="company1"></slot>
          </li>
          <li class="col-sm-8 col-md-4">
              <slot name="company2"></slot>
          </li>
          <li class="col-sm-8 col-md-4">
              <slot name="company3"></slot>
          </li>
        </ul>
        <ul class="list-inline row hidden">
          <li class="col-sm-4">
            <slot name="company4"></slot>
          </li>
          <li class="col-sm-4">
              <slot name="company5"></slot>
          </li>
          <li class="col-sm-4">
              <slot name="company6"></slot>
          </li>
        </ul>
      </div>
      <!-- Technologies -->
      <div class="panel-body custom-fa-panel-body" v-else="type === 'tools'">
        <ul class="list-inline row">
          <li class="col-sm-4">
              <slot name="tool1"></slot>
          </li>
          <li class="col-sm-4">
              <slot name="tool2"></slot>
          </li>
          <li class="col-sm-4">
              <slot name="tool3"></slot>
          </li>
        </ul>
        <ul class="list-inline row hidden">
          <li class="col-sm-4">
            <slot name="tool4"></slot>
          </li>
          <li class="col-sm-4">
              <slot name="tool5"></slot>
          </li>
          <li class="col-sm-4">
              <slot name="tool6"></slot>
          </li>
        </ul>
      </div>


    </div>
  </div>
</template>

<script>
export default {
  name: 'faPanel',
  props: {
    title:{
      type: String,
      required: true
    },
    type: {
      type: String,
      required: true
    }
  },
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
