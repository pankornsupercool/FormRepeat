<template>
    <h1>{{ msg }}</h1>
    <label v-if="label != null" for="name">{{label}}   </label>
    <input 
    :value="modelValue"
    :placeholder="label"
    @input="$emit('update:modelValue', $event.target.value)"
    />
</template>

<script>
export default {
  name: 'BaseInput',
  props: {
    label :{
      type: String,
      default: ''
    },
    modelValue :{
      type: [String,Number],
      default: ''
    }
  }
}
</script>
<style scoped>

</style>
<!-- Add "scoped" attribute to limit CSS to this component only -->
