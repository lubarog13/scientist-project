<template>
  <v-layout>
    <v-app-bar primary color="#05336e">
      <template v-slot:prepend>
        <v-app-bar-nav-icon color="white" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      </template>

      <v-app-bar-title
        ><img
          class="logo"
          src="https://etu.ru/assets/files/ru/universitet/korporativnyj-stil/logo-leti-gold-rus-2017.svg"
          alt="Логотип"
      /></v-app-bar-title>

      <template v-slot:append>
        <a href="https://github.com/lubarog13"><v-btn icon="mdi-github" color="white"></v-btn></a>
      </template>
    </v-app-bar>
    <v-navigation-drawer
        v-model="drawer"
        temporary
        style="min-width: 30%"
    >
      <v-list>
        <a :href="'#title-'+index" v-for="(title, index) in titles" :key="index"><v-list-item :title="title" :value="`title-${index}`"></v-list-item></a>
      </v-list>
      <template v-slot:append>
        <div class="pa-2">
          <a href="https://etu.ru/">
          <v-btn block>
            СПБГЭТУ "ЛЭТИ"
          </v-btn>
          </a>
        </div>
      </template>
    </v-navigation-drawer>
  </v-layout>
</template>

<script>
import textMixin from "@/mixins/textMixin";
export default {
  name: "Header",
  mixins: [textMixin],
  data() {
    return {
      drawer: null
    }
  },
};
</script>

<style scoped>
.logo {
  height: 48px;
}
::v-deep .v-list-item:hover {
  color: #bb8d54;
}
img {
  box-shadow: none;
}
a {
  text-decoration: none;
  color: inherit;
}
</style>
