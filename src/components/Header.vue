<template>
  <div>
    <v-app-bar app color="primary" dark>
      <v-btn fab dark color="accent" small @click="drawer = true">
        <v-icon dark>menu</v-icon>
      </v-btn>
      <v-spacer></v-spacer>
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://www.gustavodiosa.com/img/logo.png"
          transition="scale-transition"
          width="140"
        />
      </div>
    </v-app-bar>
    <v-navigation-drawer
      v-model="drawer"
      :color="color"
      :permanent="permanent"
      absolute
      dark
      temporary
    >
      <v-list dense nav class="py-0">
        <v-list-item two-line>
          <v-list-item-avatar>
            <img src="https://randomuser.me/api/portraits/men/81.jpg" />
          </v-list-item-avatar>

          <v-list-item-content>
            <v-list-item-title>Gustavo Diosa</v-list-item-title>
            <v-list-item-subtitle>Web Developer</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>

        <v-divider></v-divider>

        <v-list-item v-for="item in items" :key="item.title" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>
<script>
export default {
  data() {
    return {
      drawer: false,
      items: [
        { title: "Dashboard", icon: "android" },
        { title: "Photos", icon: "image" },
        { title: "About", icon: "android" }
      ],
      color: "dark",
      permanent: false,
      background: false
    };
  },
  methods: {
    
  }
};
</script>
