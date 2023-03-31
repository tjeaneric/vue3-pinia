<script setup>
import { useAuthStore } from '../stores/userAuth'

const authStatus = useAuthStore()
</script>
<template>
  <button @click="authStatus.login" v-if="!authStatus.isLoggedIn">Login</button>
  <button @click="authStatus.logout" v-if="authStatus.isLoggedIn">Logout</button>
</template>
