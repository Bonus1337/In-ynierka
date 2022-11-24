<template>
  <v-app id="inspire">
    <v-navigation-drawer
      v-model="drawer"
      :clipped="$vuetify.breakpoint.lgAndUp"
      fixed
      app
    >
      <v-list dense>
        <template v-for="item in items">
          <v-list-tile :key="item.text" @click="$router.push(item.link)">
            <v-list-tile-content>
              <v-list-tile-title class="column">
                <v-icon>{{ item.icon }}</v-icon> {{ item.text }}
              </v-list-tile-title>
              <hr />
            </v-list-tile-content>
          </v-list-tile>
        </template>
        <v-list-tile key="Wyloguj" @click="logout">
          <v-list-tile-content>
            <v-list-tile-title class="column logout-button">
              Wyloguj
            </v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>

    <v-toolbar
      :clipped-left="$vuetify.breakpoint.lgAndUp"
      color="blue darken-3"
      dark
      app
      fixed
    >
      <v-toolbar-title style="width: 300px" class="ml-0 pl-3">
        <v-toolbar-side-icon @click.stop="drawer = !drawer"
          ><span><v-icon>mdi-menu</v-icon></span></v-toolbar-side-icon
        >
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn @click.native="logout" icon>
        <v-icon>mdi-exit-to-app</v-icon>
      </v-btn>
    </v-toolbar>
    <v-content>
      <router-view />
    </v-content>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    dialog: false,
    drawer: null,
    items: [
      {
        icon: "mdi-view-dashboard",
        text: "Profil użytkownika",
        link: "/dashboard",
      },
      { icon: "mdi-book", text: "Dziennik praktyk", link: "/dashboard/diary" },
      { icon: "mdi-contacts", text: "Pracodawcy", link: "/dashboard/users" },
      {
        icon: "mdi-file-document-outline",
        text: "Dokumenty",
        link: "/dashboard/documents",
      },
      { icon: "mdi-help-circle", text: "Poradnik", link: "/dashboard/history" },
      
    ],
  }),
  methods: {
    logout() {
      localStorage.removeItem("loggedIn");
      this.$router.push("/");
    },
  },
};
</script>

<style scoped>
.v-toolbar {
  flex: 0 1 auto;
}
.column {
  display: flex;
  flex-direction: column;
  text-align: center;
  margin: 10px;
  font-size: 15px;
  font-weight: bold;
}
.logout-button {
  color: red;
}
.column:hover {
  cursor: pointer;
}
</style>
