<template>
  <div id="app">
    <ul id="menu-steps">
      <li @click="changeComponent('Step1')">Step 1</li>
      <li @click="changeComponent('Step2')">Step 2</li>
      <li @click="changeComponent('Step3')">Step 3</li>
    </ul>
    <div class="clb"></div>
    <div id="bg-progress-bar" :class="currentTabComponent">
      <div id="progress-bar"></div>
      <div id="point"></div>
    </div>
    <component
      :is="currentTabComponent"
      :currentTabComponent.sync="currentTabComponent"></component>
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
body {
  background-color: #e0e1e2;
}

#app {
  width: 75%;
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 5px 25px rgba(0, 0, 0, .2);
  color: #2c3e50;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  margin: 60px auto;
  padding: 90px 25px 50px 25px;
  position: relative;
  text-align: center;
}

#menu-steps {
  width: 100%;
  height: 40px;
  list-style-type: none;
  list-style-position: inside;
  margin: 0;
  padding: 0;
  position: absolute;
  top: 0;
  left: 0;
  > li {
    width: 33.33333333%;
    height: 40px;
    line-height: 40px;
    float: left;
    font-weight: bold;
    &:first-of-type {
      border-radius: 8px 0 0 0;
    }
    &:last-of-type {
      border-radius: 0 8px 0 0;
    }
    &:hover {
      background-color: #f0f1f2;
      color: grey;
      cursor: pointer;
    }
  }
}

#bg-progress-bar {
  width: 100%;
  height: 5px;
  background-color: #e0e1e2;
  position: absolute;
  top: 40px;
  left: 0;
  > #progress-bar {
    height: 5px;
    background-color: #53B983;
    position: absolute;
    top: 0;
    left: 0;
    transition: width .2s;
  }
  > #point {
    width: 14px;
    height: 14px;
    background-color: #53B983;
    border-radius: 50%;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    transition: left .2s;
  }
  &.Step1 {
    > #progress-bar {
      width: 16%;
    }
    > #point {
      left: 16%;
    }
  }
  &.Step2 {
    > #progress-bar {
      width: 50%;
    }
    > #point {
      left: 50%;
    }
  }
  &.Step3 {
    > #progress-bar {
      width: 83%;
    }
    > #point {
      left: 83%;
    }
  }
}

.btn-prev,
.btn-next {
  height: 40px;
  line-height: 40px;
  background-color: white;
  border-top: 1px solid #ccc;
  border-bottom: none;
  font-weight: bold;
  padding: 0 40px;
  position: absolute;
  bottom: 0;
  text-transform: uppercase;
  &:hover {
    background-color: #f0f1f2;
    cursor: pointer;
  }
}

.btn-prev {
  border-right: 1px solid #ccc;
  border-left: none;
  border-radius: 0 0 0 8px;
  left: 0;
}

.btn-next {
  border-left: 1px solid #ccc;
  border-right: none;
  border-radius: 0 0 8px 0;
  right: 0;
}

.clb {
  clear: both;
}
</style>
