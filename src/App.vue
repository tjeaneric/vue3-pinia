<script setup>
import BaseContainer from './components/BaseContainer.vue'
import ChangeCounter from './components/ChangeCounter.vue'
import UserAuth from './components/UserAuth.vue'
import { useCounterStore } from './stores/counter'
import { useAuthStore } from './stores/userAuth'
import { storeToRefs } from 'pinia'

const counter = useCounterStore()
const authStatus = useAuthStore()

const { count, doubleCount } = storeToRefs(counter)
const { isLoggedIn } = storeToRefs(authStatus)
const { increment, increase } = counter
</script>

<template>
  <base-container title="Pinia" v-if="isLoggedIn">
    <h3 v-text="doubleCount"></h3>
    <button @click="increment">Add 1</button>
    <button @click="increase(3)">Increase by 3</button>
    <ChangeCounter />
  </base-container>
  <base-container title="Auth">
    <UserAuth />
  </base-container>
</template>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>
