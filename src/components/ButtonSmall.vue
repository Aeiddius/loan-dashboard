<template>
  <button type="button">{{ name }}</button>
</template>

<script lang="ts" setup>
defineProps({
  name: {
    type: String,
    default: '[name]'
  }
})
</script>

<style lang="scss" scoped>
button {
  @include roboto-regular;
  font-size: smaller;
  color: $fade;
  transition: all 0.5s ease;
  text-decoration: none;
  background-color: transparent;
  border: none;

  &:hover {
    cursor: pointer;
    text-decoration: underline;
  }
}
</style>