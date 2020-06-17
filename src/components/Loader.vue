<template>
<div>
  <div>
    <img class="areylogo" ref="arey" src="../assets/arey.svg"/>
    <span class="nameend" style="color: #C4C4C4">lbert</span>
  </div>
  <div id="cs"></div>
  <div class="cards">
    <card v-for="(c, i) in cards" :msg="c" :key="i"></card>
  </div>
  <!-- <div>
    <a href="">
      <img src="../assets/github.png" alt="">
    </a>
  </div> -->
</div>
</template>

<script>
import "../jimson.js"
import card from "./card"

export default {
  components:{
    card: card
  },
  props: {
    msg: String
  },
  data: function(){
    return {
        cards:[
          {
            title: "Skills",
            content:[
              {
                name: "AngularJs"
              },
              {
                name: "Js"
              },
              {
                name: "VueJs"
              },
              {
                name: "Java"
              },
              {
                name: "Html"
              },
              {
                name: "C#"
              },
            ]
          },
          {
            title: "Interests",
            content:[
              {
                name: "AI"
              },
              {
                name: "IOT"
              },
              {
                name: "Automation"
              },
              {
                name: "Neurology"
              },
              {
                name: "Nano tech"
              },
              {
                name: "Elon musk"
              },
            ]
          },
          {
            title: "Projects",
            content:[
              {
                name: "Ofys",
                url: "https://ofys.ca/en/index.html"
              },
              {
                name: "Syra",
                url: "http://medoffice.ca/"
              },
              {
                name: "Sofy"
              },
              {
                name: "Upixelated"
              },
            ]
          },
          {
            title: "Meta",
            content:[
              {
                name: "About",
                description: "I am a developer with taste. I love elegant code with simple solutions to complex problems."
              },
              {
                name: "Goals",
                description: "Solve intelligence. Build world changing products. Optimize the future and find a way or make a way."
              },
            ]
          },
        ],
        particleConfig:{
        particles: {
          number: { value: 80, density: { enable: true, value_area: 800 } },
          color: { value: "#fff" },
          shape: {
            type: "polygon",
            stroke: { width: 0, color: "#fff" },
            polygon: { nb_sides: 6 },
            image: { src: "img/github.svg", width: 100, height: 100 }
          },
          opacity: {
            value: 0.5,
            random: false,
            anim: { enable: false, speed: 1, opacity_min: 0.1, sync: false }
          },
          size: {
            value: 3,
            random: true,
            anim: { enable: false, speed: 40, size_min: 0.1, sync: false }
          },
          line_linked: {
            enable: true,
            distance: 50,
            color: "#ffffff",
            opacity: 0.4,
            width: 1
          },
          move: {
            enable: true,
            speed: 1,
            direction: "bottom",
            random: true,
            straight: true,
            out_mode: "out",
            bounce: false,
            attract: { enable: true, rotateX: 600, rotateY: 1200 }
          }
        },
        interactivity: {
          detect_on: "canvas",
          events: {
            onhover: { enable: true, mode: "bubble" },
            onclick: { enable: true, mode: "repulse" },
            resize: true
          },
          modes: {
            grab: { distance: 50, line_linked: { opacity: 1 } },
            bubble: {
              distance: 50,
              size: 5,
              duration: 2,
              opacity: 2,
              speed: 3
            },
            repulse: { distance: 200, duration: 0.4 },
            push: { particles_nb: 4 },
            remove: { particles_nb: 2 }
          }
        },
        retina_detect: true
        }
      };
  },
  methods:{
    initAreyLogo: function (canvas){
      const ctx = canvas.getContext('2d');
      var paths = [
        // new Path2D("M45.3045 127.419L41.0572 119.531L22.6522 148.858L45.3045 127.419Z"),
        // new Path2D("M74.0243 127.419L79.4851 121.958L97.8901 151.891L74.0243 127.419Z"),
        // new Path2D("M50.1586 94.4518L59.8667 55.4171L70.586 94.4518L59.8667 109.216L50.1586 94.4518Z"),

        new Path2D("M82.3045 146.419L78.0572 138.531L59.6522 167.858L82.3045 146.419Z"),
        new Path2D("M111.024 146.419L116.485 140.958L134.89 170.891L111.024 146.419Z"),
        new Path2D("M87.1585 113.452L96.8666 74.4171L107.586 113.452L96.8666 128.216L87.1585 113.452Z"),
        // new Path2D("M70.5927 69.345C74.0376 48.8866 94.7909 5.74147 103.166 0.317531C109.279 14.2295 98.4328 55.8236 70.5927 69.345Z"),
        // new Path2D("M50.0533 69.5524C46.7413 49.0721 26.2683 5.79317 17.9284 0.315007C11.725 14.187 22.3016 55.8506 50.0533 69.5524Z"),
      ]
      var wingset = [
        [
          new Path2D("M107.858 88.5818C125.007 99.6889 152.633 134.799 152.455 144.209C135.441 143.982 103.009 118.071 107.858 88.5818Z"),
          new Path2D("M86.688 89.5872C69.6673 100.456 42.3246 134.934 42.5434 144.209C59.4791 144.061 91.6473 118.671 86.688 89.5872Z"),
        ],
        [
          new Path2D("M107.155 88.5112C127.177 93.9458 168.079 118.83 172.656 127.697C158.211 132.416 117.881 117.543 107.155 88.5112Z"),
          new Path2D("M86.8543 88.5112C66.8324 93.9457 25.9304 118.83 21.3539 127.697C35.7984 132.416 76.1283 117.543 86.8543 88.5112Z"),
        ],
        [
          new Path2D("M107.336 89.5233C128.406 88.3783 178.263 97.3789 186.85 103.391C175.923 111.325 131.542 110.401 107.336 89.5233Z"),
          new Path2D("M87.2046 89.4882C65.9867 88.3071 15.791 97.3351 7.15144 103.394C18.1642 111.419 62.855 110.538 87.2046 89.4882Z"),
        ],
        [
          new Path2D("M108.066 89.2179C128.75 80.7306 182.778 69.77 194.019 71.3583C186.478 81.4795 141.46 96.7583 108.066 89.2179Z"),
          new Path2D("M87.1 90.0307C66.3882 81.1078 12.2546 69.6651 0.980147 71.3793C8.51087 82.0701 53.5986 98.1101 87.1 90.0307Z"),
        ],
        [
          new Path2D("M107.675 88.6315C119.03 71.2688 155.336 40.0585 165.183 38.446C165.208 53.6418 138.6 87.4017 107.675 88.6315Z"),
          new Path2D("M86.982 88.6315C75.6264 71.2688 39.3205 40.0585 29.4734 38.446C29.4485 53.6418 56.0566 87.4017 86.982 88.6315Z"),
        ],
        [
          new Path2D("M107.593 88.345C111.038 67.8866 131.791 24.7415 140.166 19.3175C146.279 33.2295 135.433 74.8236 107.593 88.345Z"),
          new Path2D("M87.0533 88.5524C83.7413 68.0721 63.2683 24.7932 54.9284 19.315C48.725 33.187 59.3016 74.8506 87.0533 88.5524Z"),
        ],
        [
          new Path2D("M107.231 88.3153C104.649 65.9279 109.875 11.261 115.094 1.20219C123.54 11.7534 125.749 59.393 107.231 88.3153Z"),
          new Path2D("M87.8753 87.7643C90.399 65.2764 85.0659 10.338 79.8402 0.219731C71.4441 10.802 69.3489 58.6629 87.8753 87.7643Z"),
        ]
      ]
      var currWingset = wingset.length-2;
      var direction = 1;
      var wingspeed = 1;
      var wingframe = 0;
      function getWingsetIndex(){
        wingframe++;
        if(wingframe > wingspeed){
          wingframe = 0;
          var next = currWingset + direction;
          if(next >= wingset.length){
            direction = -1
          }else if( next <= 0){
            direction = 1
          }
          currWingset = currWingset + direction
        }
        return currWingset;
      }
      // ctx.scale(0.4, 0.4)
      ctx.fillStyle = "white";
      function animate(){
        // requestAnimationFrame(animate);
        ctx.clearRect(0,0,canvas.width, canvas.height+100 )
        paths.concat(wingset[getWingsetIndex()]).forEach(function(e, i){
          if(i === 2 ){
            ctx.fillStyle = "#0075FF"
          }else{
            ctx.fillStyle = "white"
          }
          ctx.fill(e);
        })
        
      }
      animate()
    }
  },
  mounted:function(){
    // this.initAreyLogo(this.$refs.arey);
    
    if(window.particlesJS){
      console.log("not done");
      window.particlesJS("cs", {
        particles:this.particleConfig.particles,
        interactivity:this.particleConfig.interactivity,
        retina_detect:this.particleConfig.retina_detect
      }, function() {
        // eslint-disable-next-line no-console
        console.log("callback - particles.js config loaded");
      });
      // this.initAreyLogo(this.$refs.arey.children[0]);
    }else{
      console.log("done");
      
    }
    return;
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
.nameend{
    font-size: 8em;
    margin-left: -0.21em;
}
#cs{
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
}
.cards{
  position: relative;
}
.cards .card{
  margin: 5px 1em;
}
.areylogo{
  /* height: 15em; */
}
</style>
