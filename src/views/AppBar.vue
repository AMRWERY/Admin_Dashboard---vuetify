<template>
  <v-app-bar>
    <template v-slot:image>
      <v-img gradient="to top right, rgba(19,84,122,.8), rgba(128,208,199,.8)"></v-img>
    </template>

    <v-col>
      <v-app-bar-title><v-icon>mdi mdi-monitor</v-icon> Admin Dashboard</v-app-bar-title>
    </v-col>

    <v-spacer />

    <v-menu offset-y>
      <template v-slot:activator="{ props }">
        <span style="cursor: pointer">
          <v-icon v-bind="props" class="mx-5 mr-5">
            mdi mdi-bell-ring-outline
          </v-icon>
        </span>
      </template>
      <v-list class="py-0" width="250" :items="items" style="cursor: pointer" item-props lines="three">
        <template v-slot:subtitle="{ subtitle }">
          <div v-html="subtitle"></div>
        </template>
      </v-list>
    </v-menu>

    <v-menu offset-y>
      <template v-slot:activator="{ props }">
        <span v-bind="props" style="cursor: pointer" class="mx-5 mr-10">
          <v-chip link>
            <v-badge offset-x="10" offset-y="10" color="green" dot>
              <v-avatar size="40">
                <v-img src="https://randomuser.me/api/portraits/men/85.jpg" />
              </v-avatar>
            </v-badge>
            <span>Amr Mohamed</span>
          </v-chip>
        </span>
      </template>
      <v-list width="250" class="py-0">
        <v-list-item lines="two">
          <v-list-item-avatar>
            <v-img src="https://randomuser.me/api/portraits/men/85.jpg" width="70" />
          </v-list-item-avatar>
          <v-list-item-content>
            <v-list-item-title>Amr Mohamed</v-list-item-title>
            <v-list-item-subtitle>Logged In</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
        <hr>
        <v-list density="compact" v-for="menu in menus" :key="menu" style="cursor: pointer">
          <v-list-item :prepend-icon="menu.icon" :title="menu.title" link></v-list-item>
        </v-list>
      </v-list>
    </v-menu>
  </v-app-bar>
</template>

<script>
export default {
  data: () => ({
    items: [
      { type: 'subheader', title: 'Today' },
      {
        prependAvatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
        title: 'Summer BBQ',
        subtitle: `Lorem Ipsum is simply dummy text of the printing and typesetting industry.`,
      },
      { type: 'divider', inset: true },
      {
        prependAvatar: 'https://cdn.vuetifyjs.com/images/lists/4.jpg',
        title: 'Birthday gift',
        subtitle: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry.',
      },
      { type: 'divider', inset: true },
      {
        prependAvatar: 'https://cdn.vuetifyjs.com/images/lists/5.jpg',
        title: 'Recipe to try',
        subtitle: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry.',
      },
    ],
    menus: [
      { title: 'Profile', icon: 'mdi mdi-account-circle-outline' },
      { title: 'Change Password', icon: 'mdi mdi-key' },
      { title: 'Setting', icon: 'mdi mdi-cog-outline' },
      { title: 'Logout', icon: 'mdi mdi-logout' },
    ]
  }),
}
</script>
