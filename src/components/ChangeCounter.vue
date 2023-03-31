<script setup>
import { useCounterStore } from '../stores/counter'
const counter = useCounterStore()
</script>

<template>
  <button @click="counter.increment">Add 1</button>
</template>
