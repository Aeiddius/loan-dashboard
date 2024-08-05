<template>
  <div class="title row center">
    <img class="logo" src="@/assets/images/logo.svg" alt="logo">
    <span class="name">Company</span>
  </div>
</template>

<script lang="ts" setup>

</script>

<style lang="scss" scoped>
.title {
  @include roboto-medium;
  color: white;
  font-size: 22px;
  gap: 10px;
}

$size: 30px;

.logo {
  width: $size;
  height: $size;
}
</style>