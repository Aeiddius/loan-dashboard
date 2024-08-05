<template>
  <div class="officer row space-between ">
    <div class="row align-center">
      <img src="@/assets/images/profile.svg" :alt="name">
      <div class="column">
        <span class="name">{{ name }}</span>
        <span class="email">{{ email }}</span>
      </div>
    </div>

    <span class="id">{{ id }}</span>
    <span class="loans">{{ loanCount }}</span>
  </div>
</template>

<script lang="ts" setup>
defineProps({
  img: { type: String, default: '@/' },
  name: { type: String, default: '[name]' },
  email: { type: String, default: 'john.doe@email.com' },
  id: { type: String, default: '12345678' },
  loanCount: { type: Number, default: 34 }
})
</script>

<style lang="scss" scoped>
.officer {
  width: 100%;
  height: fit-content;
  @include roboto-regular;
  font-size: 14px;
  padding-right: 30px;
  margin-bottom: 10px;
}

$size: 40px;

img {
  width: $size;
  height: $size;
  margin-right: 10px;
}

.email {
  font-size: smaller;
  color: $fade;
}
</style>