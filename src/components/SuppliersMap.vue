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
    <!-- <p>
      {{ suppliers }}
    </p> -->
    </div>
    <div style="height: 80vh">
    <LMap :zoom="zoom" :center="center">
      <LTileLayer :url="url"></LTileLayer>
      <!-- <LMarker :lat-lng="[46.03220, 2.9482]"></LMarker> -->
      <LMarker class="suppliers" v-for="supplier in suppliers" v-bind:key="supplier.id" :lat-lng="[supplier.latitude, supplier.longitude]"></LMarker>
    </LMap>
  </div>
      <!-- <div v-for="supplier in suppliers" :key='supplier.id'>
      <LMarker :lat-lng="[ :latitude="supplier.latitude", :longitude="supplier.longitude" ]"></LMarker>
      </div> -->
  </div>
</template>

<script>
import { LMap, LTileLayer, LMarker } from "vue2-leaflet";
import axios from 'axios';
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
  data() {
    return {
      message: 'Carte des fournisseurs',
      // img: '.././assets/Blockchain_Logo_250_250_001.png',
      url: "https://{s}.tile.osm.org/{z}/{x}/{y}.png",
      zoom: 6,
      center: [46.5322, 2.9482],
      bounds: null,
      suppliers: null
      // [
      //   {
      //     id: 1,
      //     latitude: 10,
      //     longitude: 10
      //   },
      //   {
      //     id: 2,
      //     latitude: 11,
      //     longitude: 9.6
      //   },
      //   {
      //     id: 3,
      //     latitude: 47.413220,
      //     longitude: -1.219482
      //   },
      //   {
      //     id: 4,
      //     latitude: 46.193220,
      //     longitude: 4.82
      //   },
      //   {
      //     id: 5,
      //     latitude: 45.193220,
      //     longitude: 6.82
      //   },
      //   {
      //     id: 6,
      //     latitude: 47.03220,
      //     longitude: -0.9482
      //   },
      //   {
      //     id: 7,
      //     latitude: 46.03220,
      //     longitude: 2.9482
      //   }
      // ]
    }
  },
  mounted () {
    axios
      .get('https://boutique/suppliers/json')
      .then(response => (this.suppliers = response.data.items))
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