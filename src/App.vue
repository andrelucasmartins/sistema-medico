<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="col-md-12">
          <h1 class="text-center mt-5">Sistema Médico</h1>
          <h2>Sintomas</h2>
          <div class="form-check form-check-inline" v-for="(name, index) in all_sintomas" :key="index">
            <input class="form-check-input" type="checkbox" :id="index" :value="index">
            <label class="form-check-label" :for="index">{{ name }}</label>
          </div>
          <hr>
          <h2>Resultado</h2>
          <div>{{  }}</div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'app',
  result: '',
  count: 0,
  methods: {
    countSintomas (count) {
      switch (count) {
        case count === 100:
          this.result = 'Gripe'
          break
        case count === 110:
          this.result = 'Gripe'
          break
        case count === 111:
          this.result = 'Gripe'
          break
        default:
          this.result = 'Insira mais dados'
          break
      }
    }
  },
  data () {
    return {
      all_sintomas: {
        1: 'Febre alta',
        2: 'Dor de cabeça',
        3: 'Dor_nos musculos',
        4: 'Dor_de_articulacoes',
        5: 'calafrios',
        6: 'tosse',
        7: 'Secreção nasal',
        8: 'Falta ar',
        9: 'Coceira pele',
        10: 'Conjuntivite',
        11: 'Automento gânglios'
      },
      doencas: [
        {
          name: 'gripe',
          sintomas: {
            1: 'Febre alta',
            2: 'Dor de cabeça',
            3: 'Dor_nos musculos',
            5: 'calafrios',
            6: 'tosse',
            7: 'Secreção nasal'
          }
        },
        {
          name: 'gripe Suína',
          sintomas: {
            1: 'Febre alta',
            2: 'Dor de cabeça',
            3: 'Dor_nos musculos',
            4: 'Dor_de_articulacoes',
            5: 'calafrios',
            6: 'tosse',
            8: 'Falta ar'
          }
        },
        {
          name: 'Zica',
          sintomas: {
            1: 'Febre alta',
            2: 'Dor de cabeça',
            3: 'Dor_nos musculos',
            4: 'Dor_de_articulacoes',
            9: 'Coceira pele',
            10: 'Conjuntivite',
            11: 'Automento gânglios'
          }
        }
      ]
    }
  }
}
</script>
<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
