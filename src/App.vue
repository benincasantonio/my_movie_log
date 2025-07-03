<script setup lang="ts">
import { RouterView } from 'vue-router'
import Button from './components/ui/button/Button.vue';
import {useClipboard} from '@vueuse/core'
const clipboard = useClipboard();

function copyToClipboard() {
  if(clipboard.isSupported) {
    clipboard.copy('Hello World!')
  } else { 
    alert('Clipboard copy is not supported by this browser')
  }
}
</script>

<template>
  <RouterView />
  <Button @click="copyToClipboard">Copy to clipboard</Button>
</template>

<style scoped>
</style>
