<template>
  <div id="app">
    <!--<img src="./assets/logo.png">
    <h1></h1>
    <h2>Essential Links</h2>
    <ul>
      <li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
      <li><a href="https://gitter.im/vuejs/vue" target="_blank">Gitter Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
      <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
      <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
    </ul>-->
    <v-app height="415px" dark id="e3" standalone>
      <v-navigation-drawer class="pb-0" persistent absolute height="100%" clipped enable-resize-watcher v-model="drawer">
        <v-list dense>
          <v-list-tile v-for="item in items" :key="item">
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title>
                {{ item.text }}
              </v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
          <v-subheader class="mt-3 grey--text text--darken-1">SUBSCRIPTIONS</v-subheader>
          <v-list>
            <v-list-tile v-for="item in items2" :key="item" avatar>
              <v-list-tile-avatar>
                <img :src="`https://randomuser.me/api/portraits/men/${item.picture}.jpg`" alt="">
              </v-list-tile-avatar>
              <v-list-tile-title v-text="item.text"></v-list-tile-title>
            </v-list-tile>
          </v-list>
          <v-list-tile class="mt-3">
            <v-list-tile-action>
              <v-icon class="grey--text text--darken-1">add_circle_outline</v-icon>
            </v-list-tile-action>
            <v-list-tile-title class="grey--text text--darken-1">Browse Channels</v-list-tile-title>
          </v-list-tile>
          <v-list-tile>
            <v-list-tile-action>
              <v-icon class="grey--text text--darken-1">settings</v-icon>
            </v-list-tile-action>
            <v-list-tile-title class="grey--text text--darken-1">Manage Subscriptions</v-list-tile-title>
          </v-list-tile>
        </v-list>
      </v-navigation-drawer>
      <v-toolbar class="red">
        <v-toolbar-title>
          <v-toolbar-side-icon @click.native.stop="drawer = !drawer"></v-toolbar-side-icon>
          <v-icon fa fa-fw class="ml-3">youtube</v-icon>
        </v-toolbar-title>
        <v-spacer></v-spacer>
        <v-text-field label="Search..." single-line append-icon="search" dark hide-details></v-text-field>
      </v-toolbar>
      <main>
        <v-container>
          <v-layout>
            <v-flex xs12>
              <v-card height="300px"></v-card>
            </v-flex>
          </v-layout>
        </v-container>
      </main>
    </v-app>
  </div>
</template>

<script>
  export default {
    name: 'app',
    data() {
      return {
        msg: 'Welcome to Your Vue.js App',
        drawer: true,
        items: [
          { icon: 'trending_up', text: 'Most Popular' },
          { icon: 'subscriptions', text: 'Subscriptions' },
          { icon: 'history', text: 'History' },
          { icon: 'featured_play_list', text: 'Playlists' },
          { icon: 'watch_later', text: 'Watch Later' }
        ],
        items2: [
          { picture: 28, text: 'Joseph' },
          { picture: 38, text: 'Apple' },
          { picture: 48, text: 'Xbox Ahoy' },
          { picture: 58, text: 'Nokia' },
          { picture: 78, text: 'MKBHD' },
        ]
      }
    }
  }
</script>

<style lang="scss">
#e3, #e3 .container {
    min-height: 700px;
    overflow: hidden;
    z-index: 0;
  }

  #e3 .input-group__details:after {
    background-color: rgba(255,255,255,0.32) !important;
  }

  #e3 .input-group--focused .input-group__append-icon {
    color: inherit !important;
  }
</style>