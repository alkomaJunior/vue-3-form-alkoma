<template>
  <label v-if="label">{{ label }}</label>
  <select
    :value="modelValue"
    v-bind="{
      ...$attrs,
      onInput: ($event) => {
        $emit('update:modelValue', $event.target.value)
      },
    }"
    class="field"
  >
    <option value="" disabled selected hidden>{{ label }}</option>
    <option
      v-for="option in options"
      :key="option"
      :selected="option === modelValue"
      :value="option"
    >
      {{ option }}
    </option>
  </select>
</template>

<script>
export default {
  name: 'BaseSelect',
  props: {
    label: {
      type: String,
      default: '',
    },
    modelValue: {
      type: [String, Number],
      default: '',
    },
    options: {
      type: Array,
      required: true,
    },
  },
}
</script>

<style scoped></style>
