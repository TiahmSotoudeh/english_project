<template>
  <v-app light>
    <v-navigation-drawer
      persistent
      v-model="drawer"
      enable-resize-watcher
      fixed
      app
    >
      <v-list>
        <v-list-tile
          value="true"
          v-for="(item, i) in items"
          :key="i"
        >
          <v-list-tile-action>
            <v-icon v-html="item.icon"></v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
      <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title v-text="title"></v-toolbar-title>
      <v-spacer></v-spacer>
    <v-content>
      <router-view/>
    </v-content>
    <v-footer :fixed="fixed" app>
      <span>&copy; 2017</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      drawer: true,
      fixed: false,
      items: [
        {
          icon: 'home',
          title: 'introduction'
        },
        {
          icon: 'format_quote',
          title: 'quote 1'
        },
        {
          icon: 'format_quote',
          title: 'quote 2'
        },
        {
          icon: 'format_quote',
          title: 'quote 3'
        },
        {
          icon: 'close',
          title: 'conclusion'
        },
      ],
      title: 'english eq project'
    }
  },
  name: 'App'
}
</script>
