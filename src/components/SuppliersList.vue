<template>
  <div class="hello">
    <!-- <h1>{{ msg }}</h1> -->
    <h1>{{ message }}</h1>
    <div>
      <img alt="Vue logo" src=".././assets/CryptoDox_Blockchain_500_130_004.jpg">
      <!-- <img alt="Vue logo" :src="img"> -->
    </div>
    <br>
    <p>
      Notice d'utilisation,<br>
      visitez
      <a href="https://elduke3d.com" target="_blank" rel="noopener">mon site bidon</a>.
    </p>
    <br>
    <hr>
    <div v-for="supplier in suppliers" :key='supplier.id'>
    <!-- <Suppliers :name="PharmaStup" :status="false" :checkedAt="new Date()" /> -->
    <Suppliers :name="supplier.name" :status="supplier.status" :checkedAt="supplier.checkedAt" />
    <br>
    <hr>
    </div>
  </div>
</template>

<script>
import Suppliers from './Suppliers'
export default {
  name: 'Liste',
  components: {
    Suppliers,
  },
  props: {
    msg: String
  },
  data(){
    return{
      message: 'Liste des fournisseurs',
      suppliers: [
        //  {
        //   name: 'PharaStup',
        //   status: 'false',
        //   checkedAt: new Date(),
        //  },
        {
          id: 1,
          name: "Fournisseur 1 ?",
          status: true,
          checkedAt: new Date()
        },
        {
          id: 2,
          name: "Fournisseur 2",
          status: false,
          checkedAt: new Date()
        }
      ]
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