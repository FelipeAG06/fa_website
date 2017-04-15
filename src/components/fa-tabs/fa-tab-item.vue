<template>
    <div id="faTabItem">
      <ul class="nav nav-tabs">
          <li role="presentation" v-bind:class="[{'active':tab.active}]" v-for="tab in tablist">
            <a href="#" role="tab" data-toggle="tab">{{tab.title}}</a>
          </li>
      </ul>
      <div class="tab-content">
          <slot></slot>
      </div>
    </div>
</template>
<script>
export default{
  name: 'faTabItem',
  inherit: true,
  data () {
    return {
      tablist: []
    }
  },
  // methods:{
  mounted: function() {
    var that = this;
    this.$parent.$children.forEach(function(v){
      that.tablist.push({
          'name': v.name,
          'title': v.title,
          'active': v.active
      });
    });
    console.log(this.tablist);
  }
  // }
}
</script>
<style>
  .nav-tabs {
    background-color: #eeeeee;
    padding-top:5px;
    padding-left:5px;
    border: 1px solid #ddd;
  }
  .tab-content {
    color : #000000;
    background-color: #ffffff;
    padding : 5px 15px;
    margin-top: -1px;
    border: 1px solid #ddd;
  }
</style>
