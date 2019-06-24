<template>
  <div>
    <div class="prev-step" @click="changeStep('Step1')">
      1- Step1
    </div>
    <p>
      <b>2- Step2</b>
    </p>
    <p>
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
