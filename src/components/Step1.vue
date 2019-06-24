<template>
  <div>
    <p>
      <b>1- Step1</b>
    </p>
    <button
      type="button"
      class="btn-next"
      @click="changeStep('Step2')">
      Continuar
    </button>
  </div>
</template>

<script>
export default {
  name: 'step1',
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
