<script setup lang="ts">
import Corbado from "@corbado/web-js"

const user = Corbado.user

async function handleLogout() {
  await Corbado.logout()
  await navigateTo("/")
}
</script>

<template>
  <div>
    <div v-if="user">
      <h1>Profile Page</h1>
      <p>
        User-ID: {{ user.sub }}
        <br />
        Email: {{ user.email }}
      </p>
      <button @click="handleLogout">Logout</button>
    </div>

    <!-- Show the "not logged in" message if the user is not logged in -->
    <div v-else>
      <p>You're not logged in.</p>
      <p>
        Please go back to <NuxtLink href="/">home</NuxtLink> to log in.
      </p>
    </div>
  </div>
</template>