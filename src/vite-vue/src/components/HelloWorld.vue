<script setup lang="ts">
import { ref } from 'vue'

// defineProps<{ msg: string }>()

const msg = ref('')

const getMessage  = async () => {
  msg.value = await fetch('/api/messages/hello')
  .then(res => res.text())
  .then(msg => msg)
}

getMessage()
</script>

<script lang="ts">
export default {};
</script>

<template>
  <div>
    {{msg}}
  </div>
</template>
