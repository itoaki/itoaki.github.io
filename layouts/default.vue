<template>
  <v-app>
    <!-- header -->
    <v-app-bar clipped-left app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="title" />
    </v-app-bar>

    <!-- sidebar -->
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="minivariant"
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
        <!-- TODO Collapse sidebar -->
        <v-list-item @click.stop="minivariant = !minivariant">
          <v-list-item-action>
            <v-icon>>></v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Collapse sidebar</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <!-- content -->
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <!-- footer -->
    <v-footer fixed app>
      <span>&copy; 2019 itoaki.github.io</span>
    </v-footer>
  </v-app>
</template>
<script>
export default {
  data () {
    return {
      drawer: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      minivariant: false,
      title: 'itoaki.github.io'
    }
  }
}
</script>
