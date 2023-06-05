<script setup>
import { computed } from 'vue'
import { useVModel } from '@vueuse/core'

const props = defineProps({
  // modelValue: {
  //   type: Boolean,
  //   required: true,
  // },
})

const emit = defineEmits(['update:modelValue'])

// const proxyValue = computed({
//   get() {
//     return props.modelValue
//   },
//   set(newValue) {
//     emit('update:modelValue', newValue)
//   },
// })
// const proxyValue = useVModel(props, 'modelValue', emit)
const proxyValue = defineModel()
</script>

<template>
  <input
    type="checkbox"
    v-model="proxyValue"
    class="rounded border-gray-400 text-indigo-600 shadow-sm focus:border-indigo-300 focus:ring focus:ring-indigo-200"
  />
  <!-- <input
    type="checkbox"
    :checked="modelValue"
    @change="$emit('update:modelValue', $event.target.checked)"
    class="rounded border-gray-400 text-indigo-600 shadow-sm focus:border-indigo-300 focus:ring focus:ring-indigo-200"
  /> -->
</template>
