<script setup>
const props = defineProps({
  label: String,
  img: String,
});
const getImgSrc = () => {
  return new URL(`../assets/${props.img}.png`, import.meta.url);
};
const getImgSrcset = () => {
  return `${new URL(`../assets/${props.img}.png`, import.meta.url)}, ${new URL(
    `../assets/${props.img}@2x.png`,
    import.meta.url
  )} 2x`;
};
</script>

<template>
  <div class="icon-wrapper">
    <img
      class="icon"
      :src="getImgSrc()"
      :srcset="getImgSrcset()"
      :alt="props.label"
    />
    <div class="label">{{ props.label }}</div>
  </div>
</template>

<style scoped>
.icon-wrapper {
  cursor: grab;
  padding-bottom: 20px;
  width: fit-content;
}
.sortable-chosen {
  cursor: grabbing;
}
.icon {
  background: #c2e891;
  border-radius: 10px;
  box-shadow: 0px 1px 2px 1px rgba(0, 0, 0, 0.2);
  height: 80px;
  margin-bottom: 7px;
  width: 80px;
}
.label {
  font-family: sans-serif;
  font-size: 14px;
  text-align: center;
}
</style>
