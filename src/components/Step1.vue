<template>
  <div>
    Step1
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
