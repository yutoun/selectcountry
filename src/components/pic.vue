<template>
<div class="pic">

  <body>
    <h1 class="title">
      WORLD RECOMMENDATION
    </h1>
    <div class="bigbox">
        <div  v-for="(pic,index) in pics" key:pic.url v-if="current_slide == index" v-bind:class="{'pictures_left': item_move, 'pictures_right': item_move}">
          <img v-bind:src="pic.url">
        </div>
    </div>
    <div class="btns">
      <a class="btn-circle-3d-emboss btn1" v-on:click="onClick">LIKE</a>
      <a class="btn-circle-3d-emboss btn2" v-on:click="onClick2">NOPE</a>
    </div>
  </body>
</div>
</template>

<script>
export default {
  name: 'pic',
  data() {
    return {
      msg: 'Welcome to Your Vue.js App',
      changePic: true,
      current_slide: 0,
      item_move:'true',
      pics: [{
          url: 'https://tabippo.net/wp-content/uploads/shutterstock_218856097.jpg'
        },
        {
          url: 'https://tabippo.net/wp-content/uploads/shutterstock_236549695.jpg'
        },
        {
          url: 'https://www.ab-road.net/article/northamerica-scenic-view/misc/img/img-thumb01.jpg'
        },
        {
          url: 'https://tabippo.net/wp-content/uploads/shutterstock_210597787.jpg'
        },
        {
          url: 'https://japan-info.asia/wp-content/uploads/2018/06/Unknown-6.jpeg'
        },
        {
          url: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRPogMHp6Z0CVY4wZXHEEDwhG7u14u21gTM4LArRz0r9GDFZB_f1A&s'
        },
        {
          url: 'https://d1m1bsps9tiz0g.cloudfront.net/system/App/Blog/thumbnails/000/001/719/large/f0eeec12af972cc07f35dc58428e3a6a.jpg'
        },
        {
          url: 'https://taptrip.jp/system/App/BlogBody/photos/000/025/343/original/b56b185803318e8bdf3926147c1ae4be.jpeg'
        },
        {
          url: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRvPZNeQZcHOsmrfwfU-YPiLQ0W5uyLd7QQ0dwXqTWDPD1t35ix&s'
        },
        {
          url: 'https://x.hankyu-travel.com/photo_db/image_search_kikan5.php?p_photo_mno=00000-BP16_-04817.jpg'
        },
        {
          url: 'https://x.hankyu-travel.com/cms_photo_image/image_search_kikan3.php?p_photo_mno=00000-BP17_-07539.jpg'
        }
      ]
    }
  },
  methods: {
    onClick: function() {
      this.current_slide++;
      if (this.current_slide == this.slides.length) {
        this.current_slide = 0;
        this.item_move= 'true'
      }
    },
    onClick2: function() {
      this.current_slide++;
      if (this.current_slide == this.slides.length) {
        this.current_slide = 0;
        this.item_move= 'false'
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
body {
  margin: 0px 100px;
  height: 1000px;
}

h1 {
  text-align: center;
  color: black;
  font-size: 50px;
}

.bigbox img {
  background-color: red;
  width: 400px;
  height: 300px;
  text-align: center;
  margin: 0 auto;
}
.pictures_right{
  animation: fadeIn 0.5s;
}
.pictures_left{
  animation: fadeIn2 0.5s;
}
@keyframes fadeIn {
    from {
        opacity:0;
        transform: translate(0px);
        opacity:1;
    }
    to {
        opacity:1;
        transform: translate(-200px, -200px);
        opacity: 0
    }
}
@keyframes fadeIn2 {
    from {
        opacity:0;
        transform: translate(0px);
        opacity:1;
    }
    to {
        opacity:1;
        transform: translate(200px, -200px);
        opacity: 0
    }
}
.btn-circle-3d-emboss {
  margin-top: 40px;
  display: inline-block;
  text-decoration: none;
  color: #ffba78;
  width: 70px;
  height: 70px;
  font-size: 21px;
  line-height: 73px;
  border-radius: 50%;
  overflow: hidden;
  font-weight: bold;
  box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.29);
  border-bottom: solid 3px #d29963;
  text-shadow: -1px -1px rgba(255, 255, 255, 0.43), 1px 1px rgba(0, 0, 0, 0.49);
  transition: .4s;
}


.btn-circle-3d-emboss:active {
  -webkit-transform: translateY(2px);
  transform: translateY(2px);
  box-shadow: 0 0 2px rgba(0, 0, 0, 0.35);
  border-bottom: none;
}

.btn1 {
  margin-right: 130px;
  background: rgb(249, 34, 34);
}

.btn2 {
  background: rgb(64, 80, 222);
}
</style>
