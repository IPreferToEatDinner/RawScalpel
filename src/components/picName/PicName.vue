<template>
  <div>
    {{ PicName }}
  </div>
</template>

<style scoped lang="scss">
div {
  font-size: 20px;
}
</style>

<script setup lang="ts">
import { ref } from 'vue';

const PicName = ref('Name.raw')
</script>