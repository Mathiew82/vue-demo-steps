<template>
  <div>
    Step2
    <p>
      <button type="button" @click="changeStep('Step1')">
        Volver
      </button>
      <button type="button" @click="changeStep('Step3')">
        Continuar
      </button>
    </p>
  </div>
</template>

<script>
export default {
  name: 'step2',
  methods: {
    changeStep (comp) {
      this.$emit('changeStep', comp)
    }
  }
}
</script>
