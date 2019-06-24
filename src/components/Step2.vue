<template>
  <div>
    <p>
      <b>2- Step2</b>
    </p>
    <button
      type="button"
      class="btn-prev"
      @click="changeStep('Step1')">
      Volver
    </button>
    <button
      type="button"
      class="btn-next"
      @click="changeStep('Step3')">
      Continuar
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
    }
  }
}
</script>
