<template>
  <div id="faTabs">
    <div role="tabpanel" class="tab-pane" v-bind:class="{'active':active}" v-bind:id="name">
        <slot></slot>
    </div>
  </div>
</template>
<script>
export default{
  name: 'faTabs',
  props: {
    'title': {
      type:String,
      required: false
    },
    'active': {
      type:[Boolean,String],
      default:false
    },
    'name': {
      type:String,
      required: false
    }
  }
}
</script>
