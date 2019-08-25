<template>
  <nav>
      <v-toolbar app>
          <v-app-bar-nav-icon class="grey--text" @click="drawer = !drawer"></v-app-bar-nav-icon>
          
          <v-toolbar-title class="text-uppercase grey--text">
              <span class="font-weight-light">Admin</span>
              <span>Todo</span>
          </v-toolbar-title>
          <v-spacer></v-spacer>
          <v-btn color="grey" text dark>
              <span>Sign Out</span>
              <v-icon right>exit_to_app</v-icon>
          </v-btn>
      </v-toolbar>

      <v-navigation-drawer app v-model="drawer" class="primary" permanent>
          <v-list>
              <v-list-item v-for="link in links" :key="link.text" router :to="link.route">
                  <v-list-item-icon>
                      <v-icon class="white--text">{{link.icon}}</v-icon>
                  </v-list-item-icon>
                  <v-list-item-content>
                      <v-list-item-title class="white--text">
                          {{link.text}}
                      </v-list-item-title>
                  </v-list-item-content>
              </v-list-item>
          </v-list>
      </v-navigation-drawer>
  </nav>
</template>

<script>
export default {
    data() {
        return {
            drawer: false,
            links: [
                { icon: 'dashboard', text: 'Dashboard', route: '/' },
                { icon: 'folder', text: 'My Projects', route: '/projects' },
                { icon: 'person', text: 'Team', route: '/team' },
            ]
        }
    },

}
</script>
 