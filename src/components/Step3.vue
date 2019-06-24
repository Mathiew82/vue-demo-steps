<template>
  <div>
    Step3
    <p>
      <button type="button" @click="changeStep('Step2')">
        Volver
      </button>
      <button type="button" @click="finish">
        Finalizar
      </button>
    </p>
  </div>
</template>

<script>
export default {
  name: 'step3',
  methods: {
    changeStep (comp) {
      this.$emit('changeStep', comp)
    },
    finish () {
      console.log('Finish')
    }
  }
}
</script>
