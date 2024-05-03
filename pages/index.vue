<script setup lang="ts">
  import Corbado from "@corbado/web-js"
  import {onMounted} from "vue";

  const authElement = useState<HTMLDivElement | undefined>('authElement', () => undefined)

  onMounted(() => {
    if (authElement.value) {
      Corbado.mountAuthUI(authElement.value, {
        onLoggedIn: () => {
          navigateTo("/profile")
        },
      })
    }
  })
</script>

<template>
  <div ref="authElement"></div>
</template>