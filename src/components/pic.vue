<template>
<div class="pic">
  <body>
    <h1 class="title">
      COUNTRY RECOMMENDATION
    </h1>
    <div class="bigbox">
      <div v-for="(pic,index) in pics" key:pic.url v-if="current_slide == index" :class="[item_move ?  'pictures_right' : 'pictures_left']">
        <img v-bind:src="pic.url" >
        <p>{{pic.area}}</p>
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
      item_move: true,
      likes:[],
      nopes:[],
      pics: [{
          url: 'https://tabippo.net/wp-content/uploads/shutterstock_218856097.jpg',
          area:'SouthAmerica'
        },
        {
          url: 'https://tabippo.net/wp-content/uploads/shutterstock_236549695.jpg',
          area:'Europe'
        },
        {
          url: 'https://www.ab-road.net/article/northamerica-scenic-view/misc/img/img-thumb01.jpg',
          area:'SouthAmerica'
        },
        {
          url: 'https://tabippo.net/wp-content/uploads/shutterstock_210597787.jpg',
          area:'America'
        },
        {
          url: 'https://japan-info.asia/wp-content/uploads/2018/06/Unknown-6.jpeg',
          area:'Europe'
        },
        {
          url: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRPogMHp6Z0CVY4wZXHEEDwhG7u14u21gTM4LArRz0r9GDFZB_f1A&s',
          area:'Africa'
        },
        {
          url: 'https://d1m1bsps9tiz0g.cloudfront.net/system/App/Blog/thumbnails/000/001/719/large/f0eeec12af972cc07f35dc58428e3a6a.jpg',
          area:'Europe'
        },
        {
          url: 'https://taptrip.jp/system/App/BlogBody/photos/000/025/343/original/b56b185803318e8bdf3926147c1ae4be.jpeg',
          area:'Asia'
        },
        {
          url: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRvPZNeQZcHOsmrfwfU-YPiLQ0W5uyLd7QQ0dwXqTWDPD1t35ix&s',
          area:'SouthAmerica'
        },
        {
          url: 'https://x.hankyu-travel.com/photo_db/image_search_kikan5.php?p_photo_mno=00000-BP16_-04817.jpg',
          area:'Asia'
        },
        {
          url: 'https://x.hankyu-travel.com/cms_photo_image/image_search_kikan3.php?p_photo_mno=00000-BP17_-07539.jpg',
          area:'America'
        }
      ]
    }
  },
  methods: {
    onClick: function() {
      this.current_slide++;
      // console.log(this.current_slide, this.pics.length)
      if (this.current_slide == this.pics.length) {
        this.current_slide = 0;
      }
      this.item_move = true
      Number(this.current_slide)
      this.likes.push(this.pics.area[this.current_slide])
      console.log(this.likes)
    },

    onClick2: function() {
      this.current_slide++;
      if (this.current_slide == this.pics.length) {
        this.current_slide = 0;
      }
      this.item_move = false
      Number(this.current_slide)
      this.nopes.push(this.pics.area[this.current_slide])
      console.log(this.nopes)
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
.bigbox{
  width: 400px;
  height: 300px;
  text-align: center;
  margin: 0 auto;
  border: black 1px double;
}
.pictures_right {
  animation: fadeIn 0.8s;
}

.pictures_left {
  animation: fadeIn2 0.8s;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
    transform: translate(0px);
    opacity: 1;
  }
  50% {
    opacity: 1;
    transform: translate(-200px, -130px);
    opacity: 0
  }
  100% {
    opacity: 1;
    transform: translate(-200px, -150px);
    opacity: 0
  }
}

@keyframes fadeIn2 {
  0% {
    opacity: 0;
    transform: translate(0px);
  }
  50% {
    transform: translate(200px, -130px);
    opacity: 0.5
  }
  100% {
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
