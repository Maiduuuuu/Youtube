<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant.sync="mini"
      :clipped="clipped"
      fixed
      app
      permanent
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
    <v-app-bar 
      :clipped-left="clipped" 
      fixed
      app
    >
      <v-app-bar-nav-icon @click.stop="mini = !mini" />
      <v-toolbar-title v-text="title" />
      <v-spacer />
      
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  components: { },
  data () {
    return {
      clipped: true,
      drawer: false,
      fixed: true,
      items: [
        {
          icon: 'mdi-home-variant',
          title: 'Home',
          to: '/'
        },
        {
          icon: 'mdi-compass-outline',
          title: 'Explore',
          to: '/explore'
        },
        {
          icon: 'mdi-youtube-subscription',
          title: 'Subscriptions',
          to: '/subscriptions'
        },
        {
          icon: 'mdi-bookmark-box-multiple-outline',
          title: 'Library',
          to: '/library'
        },
        {
          icon: 'mdi-history',
          title: 'History',
          to: '/history'
        },
      ],
      mini: true,
      title: 'YouTube Logo'
    }
  }
}
</script>
<style>
  * {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }

  .mx-auto {
      max-width: 100%;
  }
</style>
