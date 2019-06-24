<template>
  <div>
    <b>Step1</b>
    <p>
      <button type="button" @click="changeStep('Step2')">
        Continuar
      </button>
    </p>
  </div>
</template>

<script>
export default {
  name: 'step1',
  methods: {
    changeStep (comp) {
      this.$emit('changeStep', comp)
    }
  }
}
</script>
