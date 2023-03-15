<template>
  <div id="app">
    <div class="container">
      <div class="row">



        <!-- Example 3 - Motorcycle - 36 images -->
        <div class="col-12 col-md-6 mb-4 card p-0">
          <!-- <h4 class="my-2 text-center">72 Images - Box Shadow</h4> -->
          <vue-three-sixty :amount=30 imagePath="https://bseen.app/assets/carSlide/" fileName="{index}.png" boxShadow>

          </vue-three-sixty>
        </div>
        <!--/ Example 3 - Motorcycle - 36 images -->

      </div>
    </div>
  </div>
</template>

<script>

import I360Viewer from './components/I360Viewer.vue'

export default {
  name: 'App',
  components: {
    VueThreeSixty: I360Viewer
  },
  mounted() {
    this.disableZoomin();
  },
  methods: {
    disableZoomin() {
      document.addEventListener("gesturestart", function (e) {
        e.preventDefault();
        document.body.style.zoom = 0.99;
      });
      document.addEventListener("gesturechange", function (e) {
        e.preventDefault();
        document.body.style.zoom = 0.99;
      });

      document.addEventListener("gestureend", function (e) {
        e.preventDefault();
        document.body.style.zoom = 1;
      });
    }
  }
}
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
</style>
