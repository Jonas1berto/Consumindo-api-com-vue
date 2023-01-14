<template>
  <div class="container grid-lg my-2 py-2 ">
    <div class="card">

      <div class="card-header p-centered">
        <h4 class="h4">Moedas convertidas.</h4>
      </div>

      <div class="card-body">
        <TableCoins :moedas="moedas" />
      </div>
    </div>
  </div>

</template>

<script>
import TableCoins from '@/components/TableCoins.vue'
import api from '@/serve/api.js'

export default {
  name: 'App',
  components: {
    TableCoins
  },
  data() {
    return {
      moedas: []
    }
  },
  created() {
    this.chamarApi()
  },
  methods: {
    async chamarApi() {
      const response = await api.all() 
      this.moedas = response.data
      
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
  margin-top: 30px;
}

body {
  background: radial-gradient(rgb(16, 13, 13), rgb(64, 65, 66)) !important;
}

.container {
  background: #333;
}

.card {
  background: linear-gradient(#333, rgb(8, 8, 8)) !important;
  color: #fff;
  box-shadow: rgb(218, 216, 216) 0px 3px 8px;
}

tr:hover {
  transition: all ease 0.6s;
  background: #4e4b4b;
}
</style>
