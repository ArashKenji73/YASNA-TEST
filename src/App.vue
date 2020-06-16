<template>
  <div id="app">
    ARASH REZAVANDI
    <AppInput @AddCounter="AddCounter"/>
    <div class="counter-wrapper">
      <AppCounter v-for="(counter, i) in counters" :key="i" :step="counter" />
    </div>
  </div>
</template>

<script>

import AppInput from '@/components/input'
import AppCounter from '@/components/counter'
export default {
  name: 'App',
  data(){
    return{
      counters: []
    }
  },
  components: {
    AppInput,
    AppCounter
  },
  methods:{
    AddCounter(stepCounter){
      this.counters.push(stepCounter);
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  width: 1140px;
  margin: 0 auto;
}

.counter-wrapper{
  padding: 1rem;
  display: flex;
  justify-content: flex-start;

}
</style>
