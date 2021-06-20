<template>
<div class="container">
  <cabecera></cabecera>
  <div id="app">

    <div class="row">
      <div class="col-md-7">
        <div class="row">
          <div class="col-md-4" v-for="mone in monedas" :key="mone.id">
            <moneda :moneda="mone" v-on:agregar-moneda="agregarMone"></moneda>
          </div>
        </div>
      </div>
      <div class="col-md-5 my-5">
        <alcancia :items="alcancia"></alcancia>
      </div>
    </div>

  </div>
</div>
</template>

<script>

import monedas from './monedas.json'
import Moneda from './components/Moneda.vue'
import Alcancia from './components/Alcancia.vue'
import Cabecera from './components/Cabecera.vue'

export default {
  name: 'app',
  components: {
    Moneda,
    Alcancia,
    Cabecera
  },
  data(){
    Cabecera
    return {
      monedas,
      alcancia:[]
    }
  },
  methods: {
    agregarMone(moneda){
      this.alcancia.push(moneda);
    }
  }
}
</script>
