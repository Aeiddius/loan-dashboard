<template>
  <div class="card" :id="name">
    <!-- Card Head Area -->
    <div class="head row">
      <span class="name">{{ name }}</span>
      <span class="head-content">
        <slot name="head-content" />
      </span>
    </div>

    <!-- Card Content Area -->
    <div :id="name + '-content'" class="content row space-between">
      <slot />
      <!-- Left Content -->
      <div :id="name + '-left'" class="left">
        <slot name="left-content" />
      </div>


      <!-- Right Content -->
      <div :id="name + '-right'" class="right">
        <slot name="right-content" />
      </div>


    </div>



  </div>
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
.card {
  width: 100%;

  @include border;
  @include roboto-regular;

  @include shadow-hover;


}

.head {
  @include border-bottom;
  @include roboto-medium;
  padding: 5px;
  padding: 3px 12px;
  justify-content: space-between;
}

.content {
  width: 100%;

  padding: 20px;
  min-height: 300px;
}
</style>