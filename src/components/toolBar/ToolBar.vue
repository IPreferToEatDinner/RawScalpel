<template>
  <div class="background">
    <div class="contain" ref="up" @click="activeMode($event, up)">

      <div class="item">
        <img :src="editMode" alt="editMode">
      </div>

      <div class="item">
        <img :src="presetMode" alt="presetMode">
      </div>

    </div>


    <div class="contain" ref="down" @click="activeMode($event, down)">

      <div class="item">
        <img :src="drag" alt="drag">
      </div>

      <div class="item">
        <img :src="zoom" alt="drag">
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.background {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  background-color: #4F3073;
  width: 45px;
  padding-left: 3px;

  .contain {
    .item {
      display: flex;
      align-items: center;
      justify-content: center;

      height: 30px;
      width: 30px;
      margin: 10px 0;

      transition: all 0.2s;

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
import presetMode from '@/assets/images/presetMode.svg';
import drag from '@/assets/images/drag.svg';
import zoom from '@/assets/images/zoom.svg'
import { Ref, ref } from 'vue';

const up: Ref = ref(null)
const down: Ref = ref(null)

enum Mode { 'editMode', 'presetMode' };

function activeMode(event: Event, container: Ref) {
  // clear active
  const clearActive = (container: Ref) => {
    (container as unknown as HTMLDivElement).childNodes.forEach((node) => {
      (node as HTMLElement).classList.remove('active')
    })
  }

  // set active class on this button
  let getNode = event.target as HTMLElement;

  if ((getNode?.parentNode as HTMLElement)?.classList.contains('item')) {
    clearActive(container)
    getNode?.parentElement?.classList.toggle('active')
  } else if (getNode.classList.contains('item')) {
    clearActive(container)
    getNode.classList.toggle('active')
  }
}

</script>
