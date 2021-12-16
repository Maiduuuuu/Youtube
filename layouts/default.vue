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
                <v-icon
                  fab
                  >{{ item.icon }}</v-icon>
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
      <v-img
          class="ml-2"
          max-height="200"
          max-width="120"
          src="/Capture.PNG"
          >
      </v-img>
      <v-spacer /> 
        
          <v-text-field
          
            class="mt-8"
            label="Search"
            solo
                >
          </v-text-field>
          <v-btn
            x-large
            width="40"
            elevation="0"
              >
            <v-icon>
              mdi-magnify
            </v-icon>
          </v-btn>
          <v-btn
            small
            fab
            elevation="0"
            color="#212121">
            <v-icon>
              mdi-microphone
            </v-icon>
          </v-btn>
  <v-spacer />
          <v-btn
            small
            elevation="0"
            fab
            >
            <v-icon>
              mdi-dots-grid
            </v-icon>
          </v-btn>
          <v-btn
            small
            elevation="0"
            fab
            class="mx-auto"
            >
            <v-icon>
              mdi-dots-vertical
            </v-icon>
          </v-btn>
          <v-btn
            large>
            <v-img 
                  src="/signin.png"
                  max-width="100"   >
            </v-img>
          </v-btn>
          
    </v-app-bar>
    
    <v-main>
      
      <v-container>
        <v-sheet
            class="mx-auto"
            max-width="2100"
          >
              <v-slide-group
                  multiple
                  show-arrows
                >
                    <v-slide-item
                        v-for="keyword in keywords"
                        :key="keyword"
                      >
                            <v-btn
                              class="mx-2"
                              active-class="purple white--text"
                              depressed
                              rounded

                            >
                            {{ keyword }}
                            </v-btn>
                  </v-slide-item>
              </v-slide-group>
        </v-sheet>
        </v-container>
        <v-container>
          <v-row>
      <v-card
        v-for="n in 30"
        :key="n"
        class="mx-2 my-2 justify-center"
        > 
        <v-responsive
          v-if="n === 2"
          :key="`width-${n}`"
          width="100%" 
        ></v-responsive>
    <v-img class="py-1"
      src="/thumbnail.jfif"
      height="190px"
      width="340px"
    ></v-img>

    <v-card-title class="py-1 pl-2">
        <v-btn
          small
          color="pink"
          fab
          class="pr-0">
          <v-icon> 
            mdi-account 
          </v-icon>
        </v-btn>
      <v-card-title
        class="pl-1"
        >
      Video {{ n }}
      </v-card-title>
    </v-card-title>

    <v-card-subtitle
      class="pa-0 pl-13">
      {{ fullnames[n] }}
    </v-card-subtitle>

    <v-card-subtitle class="pa-0 pl-13">
      7.2M views ● 2 days ago
    </v-card-subtitle>
      </v-card>
      </v-row>
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
          icon: 'mdi-play-box-multiple',
          title: 'Library',
          to: '/Library'
        },
        {
          icon: 'mdi-history',
          title: 'History',
          to: '/history'
        },
        {
          icon: 'mdi-music',
          title: 'Music',
          to: '/music'
        },
        {
          icon: 'mdi-youtube-gaming',
          title: 'Gaming',
          to: '/gaming'
        },
        {
          icon: 'mdi-newspaper-variant',
          title: 'News',
          to: '/news'
        },
        {
          icon: 'mdi-access-point',
          title: 'Live',
          to: '/live'
        },
        {
          icon: 'mdi-safety-goggles',
          title: '360° Video',
          to: '/360'
        },
        {
          icon: 'mdi-plus',
          title: 'Browse Channels',
          to: '/browse'
        },
        {
          icon: 'mdi-youtube',
          title: 'Youtube Premium',
          to: '/premium'
        },
        {
          icon: 'mdi-cog',
          title: 'Settings',
          to: '/settings'
        },
        {
          icon: 'mdi-flag',
          title: 'Report history',
          to: '/report'
        },
        {
          icon: 'mdi-help-circle',
          title: 'Help',
          to: '/help'
        },
        {
          icon: 'mdi-message-alert',
          title: 'Send feedback',
          to: '/feedback'
        },
      ],
      mini: true,
      keywords: [
          'All',
          'Gaming',
          'Spider-Man',
          'Superheroes',
          'Geometry Dash', 
          'Gaming Computers', 
          'Rap', 
          'Apex Legends', 
          'Counter-Strike: Global Offensive', 
          '3D Printing', 
          'Trailers', 
          'Comedy', 
          'Clash of Clans', 
          'Universe', 
          'Sketch Comedy',
          'Recently Uploaded',
          'MF DOOM',
          'JPEGMAFIA',
          'Underground Hip Hop',
          'League of Legends',
          'Crab Game'],
      
      fullnames: [
          'Maci Fischer',
          'Jaeden Fleming',
          'Hana Wiley',
          'Ashlynn Quinn',
          'Nico Ward',
          'Randy Horton',
          'Danika Sherman',
          'Niko Norris',
          'Dario Hansen',
          'Janet Bell',
          'Dylan Mcdowell',
          'Mira Patterson',
          'penguinz0',
          'Smii7y',
          'Leonidas Leach',
          'Salvatore Odonnell',
          'Kristopher Underwood',
          'Tucker Daugherty',
          'Arianna Booker',
          'Armani Carey',
          'Stella Bright',
          'Yair Ellis',
          'Antonio Odonnell',
          'Bobby Nicholson',
          'Barrett Martinez',
          'Charles Kidd',
          'Adrianna Conrad',
          'King Tapia',
          'Amirah Braun',
          'Sonny Garrison',
          'Donkey'],

    }
  }
}
</script>
<style>
  * {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }
</style>
