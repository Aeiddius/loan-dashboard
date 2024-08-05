<template>
  <button type="button" class="row">

    <img :src="path" :alt="img">
    <span :class="['name', group]">{{ name }}</span>
  </button>
</template>

<script lang="ts" setup>
import { computed } from 'vue';

const props = defineProps({
  img: { type: String, default: 'profile.svg' },
  name: { type: String, default: '[name]' },
  group: { type: String, default: '[group]' },
})

const path = computed(() => {
  let res = '@/assets/images/' + props.img
  res = '../assets/images/' + props.img
  return new URL(res, import.meta.url).href
})
</script>

<style lang="scss" scoped>
button {
  background-color: transparent;
  border: none;
  @include roboto-regular;
  color: white;
  text-decoration: none;
  cursor: pointer;
  font-size: small;
  margin-bottom: 7px;
  user-select: none;

  span {
    transition: all 0.4s ease;
    transform: scale(1.0);
    border-bottom: 1px transparent solid;

    &:hover {
      border-bottom: 1px white solid;
    }

    &:active {
      transform: scale(0.8);
    }
  }
}

$size: 20px;

img {
  width: $size;
  height: $size;
  margin-right: 5px;
}

@media (max-width: 1000px) {
  button {
    margin-bottom: 0px;
    transform: scale(1);
    transition: all 0.2s ease;

    &:hover {
      transform: scale(1.2);
    }

    &:active {
      transform: scale(0.8);
    }
  }
}
</style>