<script setup>
import { computed } from 'vue'
import { useVModel } from '@vueuse/core'

const props = defineProps({
  placeholder: String,
  // modelValue: {
  //   type: String,
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
    type="text"
    v-model="proxyValue"
    class="rounded-md border border-gray-400 py-2 px-3 shadow-sm focus:border-indigo-500 focus:outline-none focus:ring-indigo-500 sm:text-sm placeholder:text-slate-400 mt-1 block w-full"
    :placeholder="placeholder"
  />
  <!-- <input
    type="text"
    :value="modelValue"
    @input="$emit('update:modelValue', $event.target.value)"
    class="rounded-md border border-gray-400 py-2 px-3 shadow-sm focus:border-indigo-500 focus:outline-none focus:ring-indigo-500 sm:text-sm placeholder:text-slate-400 mt-1 block w-full"
    :placeholder="placeholder"
  /> -->
</template>
