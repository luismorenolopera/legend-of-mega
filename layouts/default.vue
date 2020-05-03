<template>
  <v-app dark>

    <v-app-bar
      app
    >
      <v-toolbar-title>{{title}}</v-toolbar-title>
      <template v-slot:extension>
        <v-tabs>
          <v-tab>úLTIMOS ANIMES</v-tab>
          <v-tab>TODOS LOS ANIMES</v-tab>
        </v-tabs>
      </template>
      <v-spacer />
      <!-- Search button -->
      <v-text-field
        class='mt-3'
        v-show='search_input'
        append-icon="mdi-magnify"
        @blur='search_input=false'
        ref='searchField'
      >
      </v-text-field>
     <v-btn
        dark
        icon
        v-show='!search_input'
        @click='openSearch()'
      >
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
      <!-- Menu button -->
      <v-menu bottom left>
        <template v-slot:activator='{ on }'>
          <v-btn
            dark
            icon
            v-on='on'
          >
            <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>
        </template>

        <v-list>
          <v-list-item
            v-for='(item, i) in items'
            :key='i'
            :to='item.to'
            router
            exact
          >
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
       
      </v-menu>

    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>

    <v-footer
      app
    >
      <span>{{title}} - &copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      search_input: false,
      title: 'LEGEND OF MEGA',
      items: [
        {
          title: 'Mi lista',
          to: '/list'
        },
        {
          title: 'Logout',
          to: '/logout'
        },
        /*{
          title: 'login',
          to: '/login'
        }*/
      ],
    }
  },
  methods: {
    openSearch () {
      this.search_input = true
      setTimeout(() => {
        this.$nextTick(this.$refs.searchField.focus)
      }, 100)
    }
  }
}
</script>
