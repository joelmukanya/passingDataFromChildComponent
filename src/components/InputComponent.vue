<template>
  <input v-model="inputData"/>
</template>

<script>
export default {
  props: [
    'modelValue'
  ],
  computed: {
    inputData: {
      get() {
        return this.modelValue;
      },
      set(value) {
        /*Emit an event that other components     will be able to listen to.
        We can emit onclick event or a custom 
        event a developer created
        */
       // Below syntax it only used in vue3
       // $emit(type of event, value)
        this.$emit('update:modelValue', value);
      }
    }
  }
}
</script>