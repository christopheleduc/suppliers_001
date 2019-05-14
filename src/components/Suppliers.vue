<template>
  <div class="hello">
    <!-- <h1>{{ msg }}</h1> -->
    <div>
      <h1>{{ name }}</h1>
      <h3 v-if="status">A du stock ? OK</h3>
      <h3 v-else>A du stock ? KO</h3>
      <h5>{{ checkedAt }}</h5>
      <!-- <img alt="Vue logo" :src="img"> -->
      <p>Nombre de fournisseurs : {{ counter }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Suppliers',
  props: {
      name: String,
      status: Boolean,
      checkedAt: Date,
  }, 
  data(){
    return{
        liste: []
    }
  },
  methods: {
     addSup () {
         this.liste.push({
            name: 'Mon fournisseur',
            status: false, // est ce qu'il y a du stock
            checkedAt: new Date() // date de la dernière mise à jour du stock
         })
     } 
  },
  computed: {
      counter () {
          return this.liste.length
      }
  },
  mounted () {
      this.liste.push({
        'name': this.name,
        'status': this.status,
        'checkedAt': this.checkedAt
      })
  }
}
</script>
