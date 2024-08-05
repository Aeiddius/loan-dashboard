<template>
  <div id="container">
    <CardSmall name="Total Revenue" value="5.8M$" subvalue="5.1 yesterday" percentage="-4.54" />
    <CardSmall name="User Count" value="1,105" subvalue="1008 yesterday" percentage="+17.15" />
    <CardSmall name="Total Loan Officer" value="54" subvalue="Check Detail" />
    <CardSmall name="Program Count" value="506" subvalue="532 Previous" percentage="-6.89" />
  </div>
</template>

<script lang="ts" setup>
import CardSmall from '@/components/CardSmall.vue';

</script>

<style lang="scss" scoped>
#container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  // gap: 10px;
}

@media (max-width: 1199px) {
  #container {
    gap: 10px;
  }

}

@media (min-width: 1200px) {
  #container {}
}

@media (min-width: 1400px) {
  #container {
    gap: 10px;
  }
}
</style>