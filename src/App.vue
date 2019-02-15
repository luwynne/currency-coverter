<template>
  <div id="app">
    <img id="appLogo" alt="Vue logo" src="./assets/logo.png">
    <h1>Coversor de moedas</h1>
    <h2>Moeda brasileira</h2>
    <div class="linha">
      <Conversor moeda-a="USD" moeda-b="BRL" />
      <Conversor moeda-a="BRL" moeda-b="USD" />
    </div>
    <div class="linha">
      <Conversor moeda-a="CAD" moeda-b="BRL" />
      <Conversor moeda-a="BRL" moeda-b="CAD" />
    </div>
    <div class="linha">
      <Conversor moeda-a="EUR" moeda-b="BRL" />
      <Conversor moeda-a="BRL" moeda-b="EUR" />
    </div>
    <div class="linha">
      <Conversor moeda-a="GBP" moeda-b="BRL" />
      <Conversor moeda-a="BRL" moeda-b="GBP" />
    </div>
    </br>
    <hr>
    <h2>Moeda internacional</h2>
     <div class="linha">
      <Conversor moeda-a="USD" moeda-b="EUR" />
      <Conversor moeda-a="EUR" moeda-b="USD" />
    </div>
    <div class="linha">
      <Conversor moeda-a="USD" moeda-b="JPY" />
      <Conversor moeda-a="JPY" moeda-b="USD" />
    </div>
    <div class="linha">
      <Conversor moeda-a="USD" moeda-b="GBP" />
      <Conversor moeda-a="GBP" moeda-b="USD" />
    </div>
    <div class="linha">
      <Conversor moeda-a="EUR" moeda-b="GBP" />
      <Conversor moeda-a="GBP" moeda-b="EUR" />
    </div>
  </div>
</template>

<script>
import Conversor from './components/Conversor.vue'

export default {
  name: 'app',
  components: {
    Conversor
  }
}
</script>

<style>
#app {
  margin: auto;
  max-width: 900px;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#appLogo{
  max-width:100px;
}

.linha{
  text-align:left!important;
  margin-top:40px;
  display:flex;
  justify-content: space-around;
}
</style>
