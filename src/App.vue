<script setup>
import { ref } from 'vue'

const name = ref('')
const newsletter = ref(false)
</script>

<template>
  <div class="max-w-xl mx-auto py-12 px-6">
    <h2 class="text-2xl font-semibold">v-model in Child Examples</h2>
    <form class="mt-6">
      <div class="mt-2">
        <input
          type="text"
          v-model="name"
          class="rounded-md border border-gray-400 py-2 px-3 shadow-sm focus:border-indigo-500 focus:outline-none focus:ring-indigo-500 sm:text-sm placeholder:text-slate-400 mt-1 block w-full"
          placeholder="Name"
        />
        <div class="mt-2">Name: {{ name }}</div>
      </div>

      <div class="mt-8">
        <label class="flex items-center">
          <input
            type="checkbox"
            v-model="newsletter"
            class="rounded border-gray-400 text-indigo-600 shadow-sm focus:border-indigo-300 focus:ring focus:ring-indigo-200"
          />
          <span class="text-sm text-gray-700 ml-2">
            Email me news and offers
          </span>
        </label>
        <div class="mt-2">Newsletter: {{ newsletter }}</div>
      </div>
    </form>
  </div>
</template>
