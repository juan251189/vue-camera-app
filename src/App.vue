<template>
  <div id="app">
    <Camera v-on:takePicture="this.takePicture"/>
    <Gallery/>

  </div>
</template>

<script>

import Camera from "./components/Camera.vue";
import Gallery from "./components/Gallery.vue";
export default {
  name: 'App',
  components: {
    Camera,
    Gallery

  },
  methods:{
    takePicture(){

      const picture= document.querySelector("canvas");

      const ctx = picture.getContext("2d");
      ctx.imageSmoothingEnabled = true;
      ctx.imageSmoothingQuality = "high";
      ctx.drawImage(document.querySelector("video"), 0, 0, picture.width, picture.height)

    }
  }


}
</script>

<style>
body {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f3f3f3;

}
</style>
