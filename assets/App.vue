<template>
  <v-app
    :dark="dark"
    :light="!dark"
    standalone
  >
    <sidebar
      :visible="sidebar.visible"
      :clipped="sidebar.clipped"
      :persistent="sidebar.persistent"
      :mini-variant="sidebar.miniVariant"
    ></sidebar>
    <v-toolbar class="elevation-0 primary" dark fixed>
      <v-btn
        icon
        @click.native.stop="sidebar.visible = !sidebar.visible"
      >
        <v-icon>menu</v-icon>
      </v-btn>
      <v-btn
        icon
        @click.native.stop="sidebar.miniVariant = !sidebar.miniVariant"
      >
        <v-icon v-html="sidebar.miniVariant ? 'chevron_right' : 'chevron_left'"></v-icon>
      </v-btn>
      <v-btn
        icon
        @click.native.stop="sidebar.clipped = !sidebar.clipped"
      >
        <v-icon>web</v-icon>
      </v-btn>
      <v-btn
        icon
        @click.native.stop="dark = !dark"
      >
        <v-icon v-html="dark ? 'brightness_high' : 'brightness_2'"></v-icon>
      </v-btn>
      <v-btn
        icon
        @click.native.stop="fixed = !fixed"
      >
        <v-icon>remove</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title"></v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        icon
        @click.native.stop="rightDrawer = !rightDrawer"
      >
        <v-icon>menu</v-icon>
      </v-btn>
    </v-toolbar>
    <main>
      <v-slide-y-transition mode="out-in">
        <router-view></router-view>
      </v-slide-y-transition>
    </main>
    <v-navigation-drawer
      temporary
      :right="right"
      v-model="rightDrawer"
    >
      <v-list>
        <v-list-tile @click.native="right = !right">
          <v-list-tile-action>
            <v-icon light>compare_arrows</v-icon>
          </v-list-tile-action>
          <v-list-tile-title>Switch drawer (click me)</v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-footer :fixed="fixed">
      <span>&copy; 2017</span>
    </v-footer>
  </v-app>
</template>

<script>
  import Meta from 'mixins/meta'
  import Sidebar from 'components/Sidebar'

  export default {
    mixins: [Meta],
    components: {
      Sidebar
    },
    data () {
      return {
        dark: false, // dark style
        sidebar: { // side bar props
          visible: true,
          clipped: true,
          miniVariant: false,
          persistent: true
        },
        fixed: true,
        items: [
          { icon: 'apps', title: 'Welcome', to: '/' },
          { icon: 'bubble_chart', title: 'Inspire', to: '/inspire' }
        ],
        right: true,
        rightDrawer: false,
        title: 'Vuetify.js'
      }
    }
  }
</script>

<style lang="stylus">
  @import './stylus/main'
</style>
