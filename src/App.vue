<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="col-md-12">
          <h1 class="text-center mt-5">Sistema Médico</h1>
          <h2>Sintomas</h2>
          <hr>
        </div>
      </div>
      <div class="row row-cols-3">
        <div class="form-check form-check-inline col" v-for="(sintoma, key, index) in all_sintomas" :key="index">
          <input class="form-check-input" type="checkbox" :id="index" :value="key" v-model.number="result">
          <label class="form-check-label" :for="index">{{ sintoma }}</label>
        </div>
      </div>
      <div class="row">
        <div class="col-md-12">
          <hr>
          <h2>Resultado</h2>
          <div class="text-danger">{{ this.countResult }}</div>
          <div class="card mt-3" style="width: 18rem;" v-for="(doenca, key , index) in doencas" :key="index" v-show="doenca.name == countResult">
            <div class="card-header">
              {{ doenca.name }}
            </div>
            <ul class="list-group list-group-flush">
              <li class="list-group-item" v-for="sintoma in doenca.sintomas" :key="sintoma.id">{{ sintoma }}</li>
            </ul>
        </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'app',
  computed: {
    countResult () {
      const r = this.result.reduce((acc, num) => acc + num, 0)
      let result
      if (r === 28) {
        result = this.doencas[0].name
      } else if (r === 46) {
        result = this.doencas[1].name
      } else if (r === 48) {
        result = this.doencas[2].name
      }
      return result
    }
  },
  data () {
    return {
      result: [],
      all_sintomas: {
        1: 'Febre alta',
        2: 'Dor de cabeça',
        3: 'Dor nos músculos',
        4: 'Dor de articulações',
        5: 'Calafrios',
        6: 'Tosse',
        7: 'Secreção nasal',
        9: 'Coceira pele',
        13: 'Conjuntivite',
        25: 'Falta de ar',
        26: 'Automento gânglios'
      },
      doencas: [
        {
          name: 'gripe',
          sintomas: {
            1: 'Febre alta',
            2: 'Dor de cabeça',
            3: 'Dor nos músculos',
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
            3: 'Dor nos músculos',
            4: 'Dor de articulações',
            5: 'calafrios',
            6: 'tosse',
            25: 'Falta de ar'
          }
        },
        {
          name: 'Zica',
          sintomas: {
            1: 'Febre alta',
            2: 'Dor de cabeça',
            3: 'Dor nos músculos',
            4: 'Dor de articulações',
            9: 'Coceira pele',
            13: 'Conjuntivite',
            26: 'Automento gânglios'
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
