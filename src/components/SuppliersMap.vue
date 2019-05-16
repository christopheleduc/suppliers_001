<template>
  <div class="hello">
    <!-- <h1>{{ msg }}</h1> -->
    <h1>{{ message }}</h1>
    <div>
      <img alt="Vue logo" src=".././assets/Terre_500_01.jpg">
    </div>
    <div>
    <br>
    <p>
      Pour une liste complete de nos tarifs,<br>
      consultez
      <a href="https://cryptodox.net" target="_blank" rel="noopener">ma fausse liste des tarifs</a>.
    </p>
    </div>
    <div style="height: 80vh">
    <LMap :zoom="zoom" :center="center">
      <LTileLayer :url="url"></LTileLayer>
      <LMarker :lat-lng="[47.413220, -1.219482]"></LMarker>
      <LMarker :lat-lng="[46.193220, 4.82]"></LMarker>
      <LMarker :lat-lng="[45.193220, 6.82]"></LMarker>
      <LMarker :lat-lng="[47.03220, -0.9482]"></LMarker>
      <LMarker :lat-lng="[46.03220, 2.9482]"></LMarker>
    </LMap>
  </div>
  </div>
</template>

<script>
import { LMap, LTileLayer, LMarker } from "vue2-leaflet";
export default {
  name: 'Carte',
  components: {
    LMap,
    LTileLayer,
    LMarker
  },  
  props: {
    msg: String
  },
  data(){
    return{
      message: 'Carte des fournisseurs',
      // img: '.././assets/Blockchain_Logo_250_250_001.png',
      url: "https://{s}.tile.osm.org/{z}/{x}/{y}.png",
      zoom: 6,
      center: [46.5322, 2.9482],
      bounds: null
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>