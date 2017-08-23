<template>
  <v-navigation-drawer
    :persistent="persistent"
    :mini-variant="miniVariant"
    :clipped="clipped"
    absolute
    enable-resize-watcher
    v-model="drawer"
  >
    <slot name="menu">
      <v-list>
        <v-list-tile
          router
          :to="item.to"
          :key="i"
          v-for="(item, i) in items"
        >
          <v-list-tile-action>
            <v-icon v-html="item.icon"></v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </slot>
  </v-navigation-drawer>
</template>

<script>
  export default {
    name: 'sidebar',
    props: ['clipped', 'mini-variant', 'persistent', 'visible'],
    data () {
      return {
        drawer: this.visible,
        items: [
          { icon: 'list', title: 'Lista', to: '/' },
          { icon: 'chrome_reader_mode', title: 'Formulario', to: '/form' }
        ]
      }
    },
    watch: {
      visible: function () {
        this.drawer = this.visible
      }
    }
  }
</script>
