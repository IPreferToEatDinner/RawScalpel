<template>
  <div>
    <img :src="settings" alt="settings">
  </div>
</template>

<style scoped lang="scss">
div {
  display: flex;
  height: 30px;
  width: 30px;
  align-items: center;
  justify-content: center;

  transition: all 0.4s;

  img {
    height: 75%;
    width: 75%;
  }
}

div:hover {
  border-radius: 4px;
  background-color: #7F64A6;
}
</style>

<script setup lang="ts">
import settings from '@/assets/images/settings.svg'
</script>