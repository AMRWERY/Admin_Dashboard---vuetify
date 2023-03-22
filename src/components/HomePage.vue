<template>
  <v-app id="inspire">

    <AppBar />

    <SideBar />

    <MainPage />

  </v-app>
</template>

<script>
import AppBar from '@/views/AppBar.vue';
import SideBar from '@/views/SideBar.vue';
import MainPage from '@/views/MainPage.vue';

export default {
  components: { AppBar, SideBar, MainPage },
}
</script>
