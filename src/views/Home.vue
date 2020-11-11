<template>
  <div class="container">
    <div class="heading">
      <div class="greet">
        <h1 style="font-weight: lighter">Hello, </h1>
        <h1 class="name" style="font-weight: 500">I'm Dilain Gunasekara </h1>
      </div>
      <div class="container">
        <div class="row">
          <div class="col-auto">
<!--            <v-btn outlined color="#00BD9D">Contact</v-btn>-->
            <v-speed-dial direction="bottom">
              <template v-slot:activator>
                  <v-btn text outlined color="#00BD9D">Contact</v-btn>
              </template>
              <v-btn dark small color="red" @click="contact(3)">
                <v-icon>mdi-email</v-icon> E-Mail
              </v-btn>
              <v-btn dark small color="black" @click="contact(1)">
                <v-icon>mdi-github</v-icon> Github
              </v-btn>
              <v-btn dark small color="indigo" @click="contact(2)">
                <v-icon>mdi-linkedin</v-icon> LinkedIn
              </v-btn>
            </v-speed-dial>
          </div>
          <div class="col-auto"><v-btn outlined color="#49C6E5" @click="getPdf">Get CV</v-btn></div>
        </div>
        <div class="imgContainer">
          <img src="~@/assets/undraw_web_developer_p3e5.svg" alt="">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  components: {
  },
  data(){
    return{
      fab: false
    }
  },
  methods:{
    contact(id){
      switch (id){
        case 1:{
          window.open('https://github.com/DSGunasekara')
          break;
        }
        case 2:{
          window.open('https://www.linkedin.com/in/adsgunasekara')
          break;
        }
        case 3:{
          window.location.href = "mailto:adsgunasekara18@gmail.com";
        }
      }
    },
    getPdf(){
      window.open('../assets/ADSGunasekara.pdf')
    }
  }
}
</script>

<style scoped>

.greet{
  padding-top: 10rem;
}

.imgContainer{
  display: none;
}

.heading {
  margin-top: -8rem;
  margin-left: 10rem;
  background-image: url("~@/assets/undraw_web_developer_p3e5.svg");
  height: auto; /* You must set a specified height */
  background-position: center; /* Center the image */
  background-repeat: no-repeat; /* Do not repeat the image */
  width: 100%;
}
.container{
  height: 75vh;
}

@media only screen and (max-width: 600px){
  .heading{
    background: none;
    /*background-image: url("~@/assets/undraw_web_developer_p3e5.svg");*/
    /*background-position: 50% 50%;*/
    /*background-size: contain;*/
    margin-left: 1rem;
    height: auto;
    width: auto;
  }
  .container{
    /*height: 100vh;*/
    margin: 0;
    height: auto;

  }
  .imgContainer{
    display: block;
  }
  .imgContainer img{
    width: 100%;
    height: auto;
    margin-top: 5rem;
  }
}

@media only screen and (max-width: 1700px){
  .heading{
    background: none;
    /*background-image: url("~@/assets/undraw_web_developer_p3e5.svg");*/
    /*background-position: 50% 50%;*/
    /*background-size: contain;*/
    margin-left: 1rem;
    height: auto;
    width: auto;
  }
  .container{
    /*height: 100vh;*/
    margin: 0;
    height: auto;

  }
  .imgContainer{
    display: block;
  }
  .imgContainer img{
    width: 100%;
    height: auto;
    margin-top: 5rem;
  }
}

</style>
