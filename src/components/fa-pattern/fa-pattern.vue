<template lang="html">
    <svg id="patternContainer" v-bind:width="screenWidth" v-bind:height="screenHeight"></svg>
</template>

<script>
  var icons = require.context('@/assets/img/home/pattern', false, /\.svg$/);
  export default {
      name: 'customPattern',
      data() {
        return {
            screenWidth: null,
            screenHeight: null
        }
      },
      mounted() {
        this.initPattern();
        this.screenWidth = window.innerWidth;
        this.screenHeight = window.innerHeight;
      },
      methods: {
        urlParse: function(path) {
         return icons('./' + path);
        },
        initPattern: function() {
          var TOTAL_ICONS = 13;
          var loadPromises = [
            this.loadSVG(this.urlParse('1.svg')),
            this.loadSVG(this.urlParse('2.svg')),
            this.loadSVG(this.urlParse('3.svg')),
            this.loadSVG(this.urlParse('4.svg')),
            this.loadSVG(this.urlParse('5.svg')),
            this.loadSVG(this.urlParse('6.svg')),
            // this.loadSVG(this.urlParse('7.svg')),
            this.loadSVG(this.urlParse('8.svg')),
            this.loadSVG(this.urlParse('9.svg')),
            this.loadSVG(this.urlParse('10.svg')),
            this.loadSVG(this.urlParse('11.svg')),
            this.loadSVG(this.urlParse('12.svg')),
            this.loadSVG(this.urlParse('13.svg'))
          ];

          Promise.all(loadPromises).then((results) => {
            this.iconsDisplay(results);
          });
         
        },
        iconsDisplay: function(results) {
          var s = Snap('#patternContainer');
          var g = s.group();
          var xAxis = 2;
          for(var i = 0; i < results.length; i++) {
            // icon.select(icon);
            var icon = results[i];
            g.append(icon);
            g.select('#' + icon.node.id).attr({
              width: 50,
              x: xAxis++ * 100,  
              y: 20
            });
          }
          
        },
        loadSVG: function(url) {
          return new Promise(function(resolve, reject) {
            Snap.load(url, resolve);
          });
        } 
      }
  }
</script>

<style lang="css">
  #patternContainer{
    position: absolute;
    z-index: 5;
  }
</style>
