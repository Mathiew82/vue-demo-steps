<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <ul>
      <li @click="changeComponent('Step1')">step 1</li>
      <li @click="changeComponent('Step2')">step 2</li>
      <li @click="changeComponent('Step3')">step 3</li>
    </ul>
    <h1>Componente</h1>
    <component :is="currentTabComponent" @changeStep="changeComponent"></component>
  </div>
</template>

<script>
import Step1 from './components/Step1'
import Step2 from './components/Step2'
import Step3 from './components/Step3'

export default {
  name: 'app',
  components: {
    Step1,
    Step2,
    Step3
  },
  data () {
    return {
      currentTabComponent: 'Step1'
    }
  },
  methods: {
    changeComponent (comp) {
      this.currentTabComponent = comp
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

button {
  background-color: #f0f1f2;
  border: 1px solid #aaa;
  font-weight: bold;
  padding: 10px 20px;
  text-transform: uppercase;
  &:hover {
    background-color: #e0e1e2;
  }
}

ul {
  list-style-type: none;
  list-style-position: inside;
  margin: 0;
  padding: 0;
  > li {
    font-weight: bold;
    &:hover {
      color: grey;
      cursor: pointer;
    }
  }
}
</style>
