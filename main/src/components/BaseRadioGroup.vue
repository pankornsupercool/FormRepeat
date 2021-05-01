<template>
  <h1>{{text}}</h1>
  <BaseRadio
    v-for="option in options"
    :key="option.value"
    :label="option.label"
    :value="option.value"
    :modelValue="modelValue"
    :name="name"
    @update:modelValue="$emit('update:modelValue', $event)"
  />
</template>

<script>
import BaseRadio from "@/components/BaseRadio.vue";

export default {
  name: "BaseRadioGroup",
  components: BaseRadio,
  props: {
    options: {
      type: Array,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    modelValue: {
      type: [String, Number],
      required: true,
    },
    text : {
        type: String,
        default: "",
    }
  },
};
</script>
