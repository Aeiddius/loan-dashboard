<template>
  <CardBig name="Loan Officers">
    <div class="column width-100">

      <OfficerItem name="John Doe" email="john.doe24@mail.com" id="87654321" :loan-count="22" />
      <OfficerItem name="Alice Johnson" email="alice.johnson7@mail.com" id="23456789" :loan-count="12" />
      <OfficerItem name="Michael Brown" email="michael.brown6@mail.com" id="34567890" :loan-count="19" />
      <OfficerItem name="Emily Davis" email="emily.davis5@mail.com" id="45678901" :loan-count="8" />
      <OfficerItem name="David Wilson" email="david.wilson8@mail.com" id="56789012" :loan-count="25" />
    </div>
  </CardBig>
</template>

<script lang="ts" setup>
import OfficerItem from '@/components/OfficerItem.vue';
import CardBig from '@/components/CardBig.vue';

</script>

<style></style>