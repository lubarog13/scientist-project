<template>
  <Header></Header>
  <v-responsive class="overflow-y-auto main">
    <v-parallax
      dark
      src="https://naukatehnika.com/files/journal/tehnika-vooruzhenie/11.02.20-grafenovyj-dvigatel/graphene-1.jpg"
    >
      <v-card
        class="title-content"
        align="center"
        elevation="2"
        justify="center"
        dark
      >
        <v-row align="center" justify="center">
          <v-col class="text-center" cols="12">
            <h1 class="text-h4 font-weight-thin mb-4">
              Жорес Иванович Алфёров
            </h1>
            <h4 class="subheading">Биография и открытия</h4>
          </v-col>
        </v-row>
      </v-card>
    </v-parallax>
    <InfoPage v-for="i in titles.length" :page-number="i - 1" />
  </v-responsive>
  <Footer></Footer>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
<script setup>
import Header from "@/components/Header.vue";
import InfoPage from "@/components/InfoPage.vue";
import Footer from "@/components/Footer.vue";
</script>
<script>
import textMixin from "@/mixins/textMixin";
export default {
  name: "App",
  mixins: [textMixin],
};
</script>
<style>
* {
  box-sizing: border-box;
}
#app {
  font-family: "Open Sans", sans-serif;
  color: #303030;
}
.main {
  height: 100%;
  overflow-y: auto;
  padding-top: 60px;
}
html,
body,
#app {
  overflow: hidden;
}
.title-content {
  width: fit-content;
  position: absolute;
  top: 50%;
  transform: translate(-50%, -50%);
  padding: 50px 80px !important;
  left: 50%;
  background: rgba(0, 0, 0, 0.7) !important;
  color: white !important;
}
.title-content h1 {
  font-size: 50px;
}
.title-content h4 {
  font-size: 36px;
}
</style>
