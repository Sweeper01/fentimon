<template>
  <v-flex xs8 offset-xs2>
    <v-layout justify-center>
      <v-card flat max-width="400">
        <v-card-title>
          <h2 class="headline">Kapitel 2</h2>
        </v-card-title>
        <v-card-text>{{ date2 }}</v-card-text>
        <v-card-text>{{ kapitel2 }}</v-card-text>
      </v-card>
    </v-layout>
  </v-flex>
</template>

<script>
export default {
  props: ["nextStep"],
  data: () => ({
    answered: false,
    date2: "23.02.2016",
    kapitel2:
      "ENDE",
  }),
};
</script>

<style>
</style>
