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
          let ITEMS_NUMBER = 40;
          let patternWidth = this.screenWidth - 140;
          let patternHeight = this.screenHeight;
          let pattern = [];

          let s = Snap('#patternContainer');
          let pastPos = 0;
          
          for (let i = 0; i < results.length; i++) {
            let itemXPos = _.random(0, patternWidth);
            let itemYPos = _.random(0, patternHeight);
            let randomIdx = _.random(0, 11);
            let randomWidth = _.random(20, 30);
            let icon = results[randomIdx];
            // pastPost = itemXPos;

            pattern.push({
              width: randomWidth,
              icon: icon,
              x: itemXPos,
              y: -itemYPos
            });
          };

          _.each(pattern, (item) => {
              s.append(item.icon);
              s.select('#' + item.icon.node.id).attr({
                width: item.width,
                x: item.x,  
                y: item.y
              });
          })


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
