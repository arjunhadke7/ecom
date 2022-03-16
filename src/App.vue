<template>
  <HelloWorld msg="This is the home page" />

  <div class="container-fluid d-print-none">
    <div class="col-sm-12 col-md-8 float-left">
      <ul class="list-group">
        <!-- <ListingComp /> -->
        <Arrtest />
      </ul>
    </div>
    
    <div class="col-sm-12 col-md-3 float-left">
      <CurrentToken />
    </div>
  </div> 

  <div class="container-fluid d-none d-print-block">
    <h3> We couldnt help but notice that you are trying to save or print customer data. </h3>

    <h3> This is Illegal and disallowed </h3>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Arrtest from "./components/Arrtest.vue";
import CurrentToken from "./components/CurrentToken.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    Arrtest,
    CurrentToken
  },
  created() {
    console.log("The listing component was created");
  },

  unmounted() {
    console.log("The listing component was Unmounted");
  },

  data() {
    return {
      // mousestatus: Boolean,
    };
  },
  methods: {
    // mouseover() {
    //   this.mousestatus = true;
    // },

    // mouseout() {
    //   this.mousestatus = false;
    // },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

@import "../node_modules/bootstrap/dist/css/bootstrap.css";
</style>
