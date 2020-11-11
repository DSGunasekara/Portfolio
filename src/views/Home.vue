<template>
  <div class="container">
    <div class="heading">
      <h1 style="font-weight: lighter">Hello, </h1>
      <h1 class="name" style="font-weight: 500">I'm Dilain Gunasekara </h1>
      <div class="container">
        <div class="row">
          <div class="col-auto"><v-btn outlined color="#00BD9D" v-bind="attrs" v-on="on">Contact</v-btn></div>
          <div class="col-auto"><v-btn outlined color="#49C6E5">Get CV</v-btn></div>
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
  }
}
</script>

<style scoped>

.heading {
  margin-top: 2rem;
  margin-left: 10rem;
  background-image: url("~@/assets/undraw_web_developer_p3e5.svg");
  height: 750px; /* You must set a specified height */
  background-position: center; /* Center the image */
  background-repeat: no-repeat; /* Do not repeat the image */
  width: auto;
}

</style>
