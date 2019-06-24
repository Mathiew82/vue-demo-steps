<template>
  <div>
    <div
      class="prev-step"
      @click="changeStep('Step1')">
      1- Step1
    </div>
    <p
      class="prev-step"
      @click="changeStep('Step2')">
      2- Step2
    </p>
    <p>
      <b>3- Step3</b>
    </p>
    <p>
      <button
        type="button"
        @click="finish">
        Finalizar
      </button>
    </p>
  </div>
</template>

<script>
export default {
  name: 'step2',
  props: [
    'currentTabComponent'
  ],
  methods: {
    changeStep (comp) {
      this.$emit('update:currentTabComponent', comp)
    },
    finish () {
      console.log('Finish')
    }
  }
}
</script>
