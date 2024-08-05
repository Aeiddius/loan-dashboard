<template>
  <div class="activity column">
    <span class="name">{{ name }}</span>
    <span class="message" v-html="messageComputed"></span>
  </div>
</template>

<script lang="ts" setup>

import { computed } from 'vue';

const props = defineProps({
  name: {
    type: String,
    default: '[name]'
  },
  message: {
    type: String,
    default: '[name]'
  }
})

const messageComputed = computed(() => {
  return props.message.replace("[", "<span class='highlight'>").replace("]", "</span>")
})
</script>

<style lang="scss" scoped>
.activity {
  @include roboto-regular;
  line-height: 15px;
  margin-bottom: 10px;
}

.message {
  font-size: 12px;
  color: $fade;
}
</style>