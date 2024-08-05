<script setup lang="ts">

import CountComp from '@/dashboard/CountComp.vue';
import RevenueComp from '@/dashboard/RevenueComp.vue';
import LoanOfficerComp from '@/dashboard/LoanOfficerComp.vue';
import ProgramImportComp from '@/dashboard/ProgramImportComp.vue';
import ActivitiesComp from '@/dashboard/ActivitiesComp.vue';

import Sidebar from '@/dashboard/SideBar.vue'
</script>

<template>
  <main class="row space-between">
    <Sidebar />

    <div id="content" class="row gap-20">
      <!-- Left -->
      <div class="column gap-20">
        <!-- Top Counts -->
        <CountComp />

        <!-- Revenue -->
        <RevenueComp />

        <!-- Loan Officer & Program Imports -->
        <div id="bottom" class="row space-between gap-20">
          <LoanOfficerComp />
          <ProgramImportComp />
        </div>

      </div>

      <!-- Right -->
      <!-- Activities -->
      <ActivitiesComp />
    </div>
  </main>
</template>


<style lang="scss">
main {
  width: 100vw;
  max-width: 100vw;
  border: none;
  width: fit-content;
  transform-origin: all 0.9s ease;
}

$content-padding: 30px;

#content {
  width: calc(100vw - $sidebarwidth);
  width: 98vw;
  padding: $content-padding;
  padding-left: $sidebarwidth + $content-padding;
}


@media (max-width: 1199px) {
  main {
    flex-direction: column !important;
    width: 100%;

  }

  #bottom {
    flex-direction: column;
  }

  #content {
    flex-direction: column;
    padding-left: $content-padding;
  }
}


@media (min-width: 1200px) {
  main {
    gap: 0px;
  }

  #content {
    flex-direction: column;
  }
}

@media (min-width: 1400px) {
  #content {
    flex-direction: row;
  }

}
</style>