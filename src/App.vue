<script setup>
import { ref } from 'vue';
import draggable from 'vuedraggable';
import Icon from './components/Icon.vue';

const icons = ref([
  { label: 'Label 1', img: 'icon1' },
  { label: 'Label 2', img: 'icon2' },
  { label: 'Label 3', img: 'icon3' },
  { label: 'Label 4', img: 'icon4' },
  { label: 'Label 5', img: 'icon5' },
  { label: 'Label 6', img: 'icon6' },
]);
</script>

<template>
  <draggable class="container" v-model="icons" tag="div" :delay="500">
    <template #item="{ element: icon }">
      <Icon v-bind="icon" />
    </template>
  </draggable>
</template>

<style scoped>
.container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  place-items: center center;
  @media (min-width: 500px) {
    grid-template-columns: 1fr 1fr 1fr 1fr;
    padding: 20px 45px;
  }
  @media (min-width: 1000px) {
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr;
    padding: 30px 60px;
  }
}
</style>
