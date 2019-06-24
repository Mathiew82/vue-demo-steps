<template>
  <div>
    <p>
      <b>3- Step3</b>
    </p>
    <button
      type="button"
      class="btn-prev"
      @click="changeStep('Step2')">
      Volver
    </button>
    <button
      type="button"
      class="btn-next"
      @click="finish">
      Finalizar
    </button>
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
