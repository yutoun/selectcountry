<template>
<div class="pic">
  <body>
    <div class="recommend" v-if="current_slide == pics.length">
      <h1 class="forU">あなたにオススメの旅行先は〜〜？ in 西欧</h1>
      <div class="bestArea">
        <img src="../../static/pix/1428178.png" class="explosion">
        <h1 class="text">{{theBest}}</h1>
      </div>
    </div>
    <div class="nomore" v-else>
      <h1 class="title">
        卒業旅こう、どこ行こう
      </h1>
      <div class="bigbox">
        <div v-for="(pic,index) in pics" key:pic.url v-if="current_slide == index" class="parents" >
          <img v-bind:src="pic.url" class="new">
          <img v-bind:src="pic.url" :class="[item_move ?  'pictures_right' : 'pictures_left']">
        </div>
      </div>
      <div class="btns">
        <a class="btn-circle-3d-emboss btn1" v-on:click="onClick">LIKE</a>
        <a class="btn-circle-3d-emboss btn2" v-on:click="onClick2">NOPE</a>
      </div>
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
      likes: [],
      nopes: [],
      theBest: '',
      pics: [
        // {
        //   url: "../../static/pix/antelopecanyon_02.jpg",
        //   area: 'アメリカアリゾナ州',
        //   country:'アメリカ南'
        // },
        // {
        //   url: "../../static/pix/borabora_01.jpg",
        //   area: 'オセアニア',
        //   country:'フランス領ポリネシア'
        // },
        {
          url: "../../static/pix/bagnoregio_03.jpg",
          area: '西ヨーロッパ',
          country:'イタリア'
        },
        // {
        //   url: "../../static/pix/canadianrockies_02.jpg",
        //   area: 'カナダ',
        //   country:'カナダ'
        // },
        // {
        //   url: "../../static/pix/kauai_01.jpg",
        //   area: 'オセアニア',
        //   country:'ハワイ'
        // },
        // {
        //   url: "../../static/pix/kelimutu_03.jpg",
        //   area: 'アジア',
        //   country:'インドネシア'
        // },
        {
          url: "../../static/pix/lampedusa_01.jpg",
          area: '西ヨーロッパ',
          country:'イタリア'
        },
        // {
        //   url: "../../static/pix/marblecathedral_01.jpg",
        //   area: '南米',
        //   country:'チリ'
        // },
        // {
        //   url: "../../static/pix/maroonbells_02.jpg",
        //   area: 'アメリカ',
        //   country:'アメリカコロラド州'
        // },
        {
          url: "../../static/pix/moher_01.jpg",
          area: '西ヨーロッパ',
          country:'アイルランド'
        },
        {
          url: "../../static/pix/plitvice_01.jpg",
          area: '中央ヨーロッパ',
          country:'クロアチア'
        },
        // {
        //   url: "../../static/pix/reed_01.jpg",
        //   area: 'アジア',
        //   country:'中国'
        // },
        // {
        //   url: "../../static/pix/roraima_01.jpg",
        //   area: '南米',
        //   country:'ブラジル'
        // },
        // {
        //   url: "../../static/pix/samui_01.jpg",
        //   area: 'アジア',
        //   country:'タイ'
        // },
        // {
        //   url: "../../static/pix/sapa_01.jpg",
        //   area: 'アジア',
        //   country:'ベトナム'
        // },
        {
          url: "../../static/pix/seljalandsfoss_01.jpg",
          area: '北欧',
          country:'アイスランド'
        },
        // {
        //   url: "../../static/pix/tekapo_01.jpg",
        //   area: 'オセアニア',
        //   country:'ニュージーランド'
        // },
        {
          url: "../../static/pix/tunnel_01.jpg",
          area: '東ヨーロッパ',
          country:'ウクライナ'
        },
        // {
        //   url: "../../static/pix/uyuni_01.jpg",
        //   area: '南米',
        //   country:'ボリビア'
        // },
        {
          url: "../../static/pix/vatnajokull_01.jpg",
          area: '',
          country:'アイスランド'
        },
        // {
        //   url: "../../static/pix/whitehaven_01.jpg",
        //   area: '',
        //   country:'オーストラリア'
        // },
        // {
        //   url: "../../static/pix/yellowstone_01.jpg",
        //   area: '北アメリカ',
        //   country:'アメリカアイダホ州'
        // },
        // {
        //   url: "../../static/pix/yellowknife_01.jpg",
        //   area: '北アメリカ',
        //   country:'カナダ'
        // },
        {
          url: "../../static/pix/zakynthos_01.jpg",
          area: '',
          country:'ギリシャ'
        }
      ]
    }
  },
  methods: {
    onClick: function() {
      this.current_slide++;
      // console.log(this.current_slide, this.pics.length)
      // if (this.current_slide == this.pics.length) {
      //   this.current_slide = 0;
      // }
      this.item_move = true
      // console.log(this.likes)
      this.likes.push(this.pics[this.current_slide - 1].area)
      console.log(this.likes)
      var mode = a => {
        a.sort((x, y) => x - y);

        var bestStreak = 1;
        var bestElem = a[0];
        var currentStreak = 1;
        var currentElem = a[0];

        for (let i = 1; i < a.length; i++) {
          if (a[i - 1] !== a[i]) {
            if (currentStreak > bestStreak) {
              bestStreak = currentStreak;
              bestElem = currentElem;
            }

            currentStreak = 0;
            currentElem = a[i];
          }

          currentStreak++;
        }

        return currentStreak > bestStreak ? currentElem : bestElem;
      };

      console.log(this.likes);
      console.log(mode(this.likes));
      console.log(mode([1, 2, 4, 1]));
      this.theBest = mode(this.likes)
    }, //このlikes(nopesは要らない)配列の中に入っている中での最頻値をtheBestに入れるのみ

    onClick2: function() {
      this.current_slide++;
      // if (this.current_slide == this.pics.length) {
      //   this.current_slide = 0;
      // }
      this.item_move = false
      this.nopes.push(this.pics[this.current_slide].area)
      console.log(this.nopes)

      var settings = {
        "async": true,
        "crossDomain": true,
        "url": "https://skyscanner-skyscanner-flight-search-v1.p.rapidapi.com/apiservices/pricing/v1.0",
        "method": "POST",
        "headers": {
          "x-rapidapi-host": "skyscanner-skyscanner-flight-search-v1.p.rapidapi.com",
          "x-rapidapi-key": "c74ace6580msh10b1b48d2da0872p10b67ajsnafd09800da28",
          "content-type": "application/x-www-form-urlencoded"
        },
        "data": {
          "inboundDate": "2019-09-10",
          "cabinClass": "business",
          "children": "0",
          "infants": "0",
          "country": "JP",
          "currency": "JPY",
          "locale": "ja-JP",
          "originPlace": "NRT-sky",
          "destinationPlace": "CTS-sky",
          "outboundDate": "2019-12-11",
          "adults": "1"
        }
      }

      axios(settings).done(function(response) {
        console.log(response);
      });
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
body {
  margin: 0px 100px;
  height: 300px;
}

.forU {
  margin-top: 50px;
}

.bestArea {
  /* animation: bigger 2s;
  animation-fill-mode: forwards;
  animation-delay: 2s; */
  animation: bigger 2s ease 0s 1 forwards;
  /* animation-delay: 2s; */
}

@keyframes bigger {
  0% {
    -webkit-transform: scale(0, 0);
    opacity: 0;
  }

  100% {
    -webkit-transform: scale(2, 2);
    opacity: 1;
  }
}

@-webkit-keyframes bigger {

  /* Safari & Chrome */
  0% {
    -webkit-transform: scale(0, 0);
  }

  100% {
    -webkit-transform: scale(2, 2);
  }
}

/* img .explosion{


} */

.text {
  position: absolute;
  top: 32%;
  /* なんで？ */
  left: 43%;
}

h1 {
  text-align: center;
  color: black;
  font-size: 50px;
}

.bigbox img {
  width: 400px;
  height: 300px;
  text-align: center;
  margin: 0 auto;
}

.parents{
  position: relative;
}

.new{
  position: absolute;
  top:0;
  left:0;
}

.bigbox {
  width: 400px;
  height: 300px;
  text-align: center;
  margin: 0 auto;
  border: black 1px double;
}

.pictures_right {
  animation: fadeIn 1s;
}

.pictures_left {
  animation: fadeIn2 1s;
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
    opacity: 1;
  }

  50% {
    opacity: 1;
    transform: translate(200px, -130px);
    opacity: 0
  }

  100% {
    opacity: 1;
    transform: translate(200px, -150px);
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
