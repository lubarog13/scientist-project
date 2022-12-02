<template>
  <v-layout>
    <v-footer color="indigo darken-1">
      <v-col class="text-center" cols="12">
        {{ new Date().getFullYear() }} — <strong>Рогозина Любовь</strong>
        <div>
          Для урока информатики
        </div>
      </v-col>
    </v-footer>
  </v-layout>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style scoped>
.bg-indigo {
  background-color: #05336e !important;
}
</style>
