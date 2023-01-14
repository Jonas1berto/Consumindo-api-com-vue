<template>
  <table class="table">
    <thead>
      <tr>
        <th>Códigos</th>
        <th>Nome</th>
        <th>Máximo</th>
        <th>Mínimo</th>
        <th>Variação</th>
        <th></th>
      </tr>
    </thead>

    <tbody>
      <tr v-for="(moeda, index) in moedas " :key="index">
        <td> {{ moeda.code }} </td>
        <td> {{ moeda.name }}</td>
        <td> {{ moeda.high }}</td>
        <td> {{ moeda.low }}</td>
        <td> 
          <span class="label label-rounded" :class=" {
          'label-error': moeda.pctChange < 0,
          'label-success': moeda.pctChange > 0,
          'label-warning': moeda.pctChange === 0
        }">
        {{ moeda.pctChange }} %
        </span> 
       </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  name: 'TableCoins',
  props: {
    moedas: {
      type: Object,
      required: true,
    }
  }
}
</script>

<style scoped>

</style>