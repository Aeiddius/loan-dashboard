<template>
  <div class="sidebar">
    <SideBarTitle />
    <hr>

    <div class="menu">

      <ButtonImg name="Dashboard" img="dashboard.svg" group="menu-btns" />
      <ButtonImg name="Profile" img="person.svg" group="menu-btns" />
      <ButtonImg name="Payments" img="payment.svg" group="menu-btns" />
      <ButtonImg name="Loans" img="loan.svg" group="menu-btns" />
      <ButtonImg name="Settings" img="setting.svg" group="menu-btns" />
      <ButtonImg name="Notifications" img="notification.svg" group="menu-btns" />
    </div>

  </div>
</template>

<script lang="ts" setup>
import ButtonImg from '@/components/ButtonImg.vue';
import SideBarTitle from '@/dashboard/SideBarTitle.vue';
</script>

<style lang="scss">
.sidebar {
  width: $sidebarwidth;
  padding: 20px;
  min-height: 100vh;
  background-color: $primary;
  position: fixed;
  height: 100%;
}

hr {
  margin: 10px 0px;
  border: 0;
  background-color: white;
  height: 1px;
}

@media (max-width: 1199px) {
  .sidebar {
    width: 100%;
    height: fit-content;
    min-height: 0px;
    position: static;
    display: flex;
    flex-direction: row;
    padding: 10px;
    align-items: center;
    justify-content: space-between;
  }

  .menu {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
  }
}


@media (max-width: 800px) {

  .menu-btns {
    display: none;
  }
}
</style>