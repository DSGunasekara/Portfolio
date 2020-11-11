<template>
  <div class="container">
    <div class="about">
      <v-row >
        <v-col >
          <img src="~@/assets/undraw_dev_productivity_umsq.svg" alt="">
        </v-col>
        <v-col class="col-auto">
          <h1 style="font-weight: 400">
            Hello
          </h1>
          <h2 style="font-weight: 400">
            I am a student of University of Sri Jayewardenepura and Sri Lanka Institute of Information
            Technology. <br>
            I have experience in frontend technologies such as <RoughNotation
              :is-show="isShow"
              type="box"
          >
            <span> Vue</span>
          </RoughNotation> and <RoughNotation
              :is-show="isShow"
              type="box"
          >
            <span> Angular</span>
          </RoughNotation> <br>
            and I have experience in working with <RoughNotation
              :is-show="isShow"
              type="underline"
          >
            <span> Django</span>
          </RoughNotation> and <RoughNotation
              :is-show="isShow"
              type="underline"
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
      window.setTimeout(this.line, 2000)
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
  width: 90%;
  height: auto;
}
@media only screen and (max-width: 600px){
  img{
    width: 100%;
    height: auto;
  }
}
</style>
