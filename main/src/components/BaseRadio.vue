<template>
<h1>This is BaseRadio</h1>
<label v-if="label">{{label}}</label>
  <input type="radio"
  :checked="modelValue === value"
  :value="value"
  v-bind="$attrs"
  @change="$emit('update:modelValue', value)"
  />
</template>

<script>
export default {
    name : "BaseRadio",
    props:{
        label:{
            type: String,
            default: ''
        },
        modelValue:{
            type : [String, Number],
            default: '',
            required: true
        },
        value : {
            type : [String, Number],
            required : true
        }
    }
}
</script>

<style>

</style>