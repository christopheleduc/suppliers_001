<template>
  <div id="app">
    <div>
      <img alt="Vue logo" src="./assets/Blockchain_Logo_250_250_001.png">
      <HelloWorld msg="GEO Loc suppliers"/>
    </div>
    <div>
      <h3>Applications</h3>
      <ul>
        <li><a @click="onSuppliersListClick">Suppliers list</a></li>
        <li><a @click="onMapClick">Suppliers map</a></li>
      </ul>
      <SuppliersList></SuppliersList>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import SuppliersList from './components/SuppliersList.vue'
import SuppliersMap from './components/SuppliersList.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    SuppliersList,
    SuppliersMap
  },
  methods: {
        onSuppliersListClick: function() {
        window.alert('UserClikerList !')
    },
        onMapClick: function(){
        window.alert('UserClikerMap !')
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
