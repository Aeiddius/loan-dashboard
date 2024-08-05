<template>
  <CardBig name="Activities">
    <template #head-content>
      <ButtonSmall name="View All" />
    </template>
    <template #left-content>
      <!-- <template v-for="num in 10" :key="num">
        <ActivityItem name="John Doe" message="Sold [Program A] to customer 1324234" />
      </template> -->


      <ActivityItem name="Alice Smith" message="Completed training on [Program B] with employee 2456738" />
      <ActivityItem name="Michael Johnson" message="Presented [Program C] to client 3478652" />
      <ActivityItem name="Emily Brown" message="Reviewed feedback for [Program D] from user 4567890" />
      <ActivityItem name="David Williams" message="Resolved issue with [Program E] for customer 5678901" />
      <ActivityItem name="Sophia Jones" message="Updated documentation for [Program F] with team member 6789012" />
      <ActivityItem name="James Garcia" message="Conducted demo of [Program G] for client 7890123" />
      <ActivityItem name="Olivia Martinez" message="Scheduled meeting for [Program H] with partner 8901234" />
      <ActivityItem name="Daniel Lee" message="Developed new feature for [Program I] with developer 9012345" />
      <ActivityItem name="Isabella Taylor" message="Analyzed data for [Program J] with analyst 1234567" />
      <ActivityItem name="Christopher Harris" message="Designed UI for [Program K] with designer 2345678" />
      <ActivityItem name="Charlotte Clark" message="Tested functionality of [Program L] with tester 3456789" />
      <ActivityItem name="Matthew Lewis" message="Launched marketing campaign for [Program M] with marketer 4567890" />
      <ActivityItem name="Ava Walker" message="Finalized contract for [Program N] with client 5678901" />
    </template>

  </CardBig>
</template>

<script lang="ts" setup>
import CardBig from '@/components/CardBig.vue';
import ActivityItem from '@/components/ActivityItem.vue';
import ButtonSmall from '@/components/ButtonSmall.vue';

</script>

<style></style>