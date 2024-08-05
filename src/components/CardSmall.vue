<template>
  <div class="card">

    <div class="left column">
      <span id="name">{{ name }}</span>
      <span id="value">{{ value }}</span>
    </div>

    <div class="right column">
      <span id="percentage" class="row center" v-if="status">
        <ArrowUp v-if="status == 'plus'" />
        <ArrowDown v-if="status == 'minus'" />
        <span :class="[status]">{{ percentage.replace("-", '').replace("+", '') }}%</span>
      </span>
      <span v-if="!status">
        <span class="hidden">hide</span>
      </span>
      <span id="subvalue">{{ subvalue }}</span>
    </div>



  </div>
</template>

<script lang="ts" setup>
import ArrowDown from '@/components/Icons/ArrowDown.vue'
import ArrowUp from '@/components/Icons/ArrowUp.vue'
import { computed } from 'vue'

const props = defineProps({
  name: {
    type: String,
    default: '[name]'
  },
  value: {
    type: String,
    default: '[value]'
  },
  percentage: {
    type: String,
    default: '[%]'
  },
  subvalue: {
    type: String,
    default: '[subvalue]'
  }
})

const status = computed(() => {
  if (props.percentage.includes("+")) return "plus"
  if (props.percentage.includes("-")) return "minus"
  return ""
})

</script>

<style lang="scss" scoped>
.card {
  width: 220px;
  // height: 60px;
  padding: 3px 12px;
  @include border;

  display: flex;
  flex-direction: row;
  justify-content: space-between;
  gap: 1px;
  @include shadow-hover;

}

.right {
  align-items: flex-end;
  justify-content: center;
  font-size: small;
}

#name {
  @include roboto-medium;
  font-size: smaller;
}

#percentage {
  @include roboto-medium;
  gap: 5px;
}

#value {
  @include roboto-regular;
  font-size: large;
}

#subvalue {
  @include roboto-regular;
  color: $fade;
  text-align: right;
}

.plus {
  color: $success;
}

.minus {
  color: $failure;
}

.hidden {
  opacity: 0;
}

@media (max-width: 850px) {
  .card {
    flex-direction: column;
  }
}
</style>