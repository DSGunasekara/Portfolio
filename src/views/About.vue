<template>
  <div class="container">
    <div class="about">
      <v-row >
        <v-col >
          <img src="~@/assets/undraw_dev_productivity_umsq.svg" alt="">
        </v-col>
        <v-col class="col">
          <h1 style="font-weight: 400">
            Hello
          </h1>
          <h2 style="font-weight: 400">
            I am a final year undergraduate of University of Sri Jayewardenepura and second year undergraduate of Sri Lanka Institute of Information
            Technology. <br>
            I have experience in frontend technologies such as <RoughNotation
              :is-show="isShow"
              type="box"
              color="#00BD9D"
          >
            <span> Vue</span>
          </RoughNotation> and <RoughNotation
              :is-show="isShow"
              type="box"
              color="#00BD9D"
          >
            <span> Angular</span>
          </RoughNotation> <br>
            and I have experience in working with <RoughNotation
              :is-show="isShow"
              type="underline"
              color="#00BD9D"
          >
            <span> Django</span>
          </RoughNotation> and <RoughNotation
              :is-show="isShow"
              type="underline"
              color="#00BD9D"
          >
            <span> Android</span>
          </RoughNotation> App Development. <br>

          </h2>
        </v-col>
      </v-row>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      isShow: false
    }
  },
  methods:{
    time(){
      window.setTimeout(this.line, 1500)
    },
    line(){
     return this.isShow = true
    }
  },
  mounted() {
    this.time()
  },
  created() {

  }
}
</script>

<style>
img{
  width: 80%;
  height: auto;
}
@media only screen and (max-width: 600px){
  img{
    width: 100%;
    height: auto;
  }
}
</style>
