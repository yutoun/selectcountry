<template>
  <div class="btn">
    <body>
      <div class="buttons">
          <a href="#" class="btn-circle-3d-emboss btn1" v-on:click="onClick">LIKE</a>
            <a href="#" class="btn-circle-3d-emboss btn2">NOPE</a>
      </div>
    </body>
  </div>
</template>

<script>
export default {
  name: 'btn',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  body{
    margin:0px 100px;
  }
  .btn-circle-3d-emboss {
    margin-top:40px;
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
.btn1{
  margin-right:130px;
  background: rgb(249, 34, 34);
}
.btn2{
  background: rgb(64, 80, 222);
}
</style>
