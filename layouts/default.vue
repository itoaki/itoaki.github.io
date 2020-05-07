<template>
  <v-app>
    <!-- sidebar -->
    <v-navigation-drawer
      v-model="drawer"
      clipped
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <!-- header -->
    <v-app-bar
      app
      dark
      clipped-left
      height="40px"
      color="#292961"
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="title" />
    </v-app-bar>
    <!-- content -->
    <v-content>
      <nuxt />
    </v-content>
    <!-- footer -->
    <v-footer
      app
      fixed
      dark
      height="30px"
      color="#292961"
    >
      <span>&copy; 2019 itoaki.github.io</span>
    </v-footer>
  </v-app>
</template>
<script>
export default {
  data () {
    return {
      title: 'itoaki.github.io(作成中)',
      drawer: false,
      items: [
        {
          icon: 'mdi-account-card-details-outline',
          title: 'Profile',
          to: '/'
        },
        {
          icon: 'mdi-desktop-mac-dashboard',
          title: 'Skill',
          to: '/skill'
        },
        {
          icon: 'mdi-widgets',
          title: 'Contents',
          to: '/contents'
        },
        {
          icon: 'mdi-account-heart',
          title: 'Accounts',
          to: '/accounts'
        }
      ]
    }
  }
}
</script>
