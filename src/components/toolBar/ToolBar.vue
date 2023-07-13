<template>
  <div class="background">
    <div class="up">
      <img :src="editMode" alt="editMode">
    </div>

  </div>
</template>

<style lang="scss" scoped>
.background {
  display: flex;
  flex-direction: columns;
  align-items: center;
  background-color: #4F3073;
  width: 45px;

  .up {
    
  }
}
</style>

<script setup lang="ts">
import editMode from '@/assets/images/editMode.svg'
</script>
