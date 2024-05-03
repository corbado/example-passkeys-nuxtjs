<script setup lang="ts">
  import Corbado from "@corbado/web-js"
  import {onMounted} from "vue";

  const isInitialized = useState('isInitialized', () => false)

  const projectId = import.meta.env.VITE_CORBADO_PROJECT_ID

  onMounted(async () => {
    await Corbado.load({
      projectId: projectId,
      darkMode: "off"
    })
    isInitialized.value = true
  })

</script>

<template>
  <div v-if="isInitialized">
    <slot/>
  </div>
</template>