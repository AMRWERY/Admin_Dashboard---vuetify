<template>
  <v-navigation-drawer v-model="drawer" :rail="rail" permanent @click="rail = false">
    <v-list-item prepend-avatar="https://randomuser.me/api/portraits/men/85.jpg" title="Admin Dashboard" nav>
      <template v-slot:append>
        <v-btn variant="text" icon="mdi-chevron-left" @click.stop="rail = !rail"></v-btn>
      </template>
    </v-list-item>

    <v-divider></v-divider>

    <v-list density="compact" nav v-for="item in items" :key="item">
      <v-list-item :prepend-icon="item.icon" :title="item.title" :value="item.value"></v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  data() {
    return {
      drawer: true,
      items: [
        { title: 'Dashboard', icon: 'mdi mdi-microsoft-windows', value: 'Dashboard' },
        { title: 'Profile', icon: 'mdi-account', value: 'Profile' },
        { title: 'Product', icon: 'mdi mdi-clipboard-list-outline', value: 'Product' },
        { title: 'Order', icon: 'mdi mdi-order-alphabetical-ascending', value: 'Order' },
        { title: 'System Settings', icon: 'mdi mdi-cog', value: 'System Settings' }
      ],
      rail: true,
    }
  }
}
</script>
