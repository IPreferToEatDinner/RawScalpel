<template>
  <div class="background">
    <div class="up" ref="up" @click.capture="activeMode">

      <div class="item">
        <img :src="editMode" alt="editMode">
      </div>

      <div class="item">
        <img :src="editMode" alt="presets">
      </div>

    </div>
    <div></div>
  </div>
</template>

<style lang="scss" scoped>
.background {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: #4F3073;
  width: 45px;
  padding-left: 3px;

  .up {
    .item {
      display: flex;
      align-items: center;
      justify-content: center;

      height: 30px;
      width: 30px;
      margin: 10px;

      transition: all 0.4s;

      img {
        height: 75%;
        width: 75%;
      }
    }

    .active {
      border-radius: 4px;
      background-color: #7F64A6;
    }
  }

  .item:hover {
    border-radius: 4px;
    background-color: #7F64A6;
  }

}
</style>

<script setup lang="ts">
import editMode from '@/assets/images/editMode.svg'
import { ref } from 'vue';

const up = ref(null)

enum Mode { 'editMode', 'presets' };

function activeMode(event: Event) {
  // set active class on this button
  let getNode = event.target as HTMLElement;
  if ((getNode?.parentNode as HTMLElement)?.classList.contains('item')) {
    (up.value as unknown as HTMLDivElement).childNodes.forEach((node) => {
      (node as HTMLElement).classList.remove('active')
    })
    getNode?.parentElement?.classList.add('active')
  }
}

</script>
