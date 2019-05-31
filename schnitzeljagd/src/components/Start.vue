<template>
  <v-container>
    <v-layout justify-center>
      <v-flex>
        <v-card>
          <v-card-title primary-title>
            <v-layout justify-center>
              <h2 class>Die Suche nach dem Geheimnis von Republika</h2>
            </v-layout>
          </v-card-title>

          <v-stepper v-model="e1">
            <v-stepper-header>
              <v-stepper-step :complete="e1 > 0" step="0">Prolog</v-stepper-step>
              <v-divider></v-divider>
              <v-stepper-step :complete="e1 > 1" step="1">Kapitel 1</v-stepper-step>
              <v-divider></v-divider>
              <v-stepper-step step="2">Kapitel 2</v-stepper-step>
            </v-stepper-header>

            <v-stepper-items>
              <v-stepper-content step="0">
                <prolog :nextStep="nextStep"></prolog>
              </v-stepper-content>
              <v-stepper-content step="1">
                <chapter1 :nextStep="nextStep"></chapter1>
              </v-stepper-content>
              <v-stepper-content step="2">
                <chapter2 :nextStep="nextStep"></chapter2>
              </v-stepper-content>
            </v-stepper-items>
          </v-stepper>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import Prolog from "@/components/Prolog";
import Chapter1 from "@/components/Chapter1";
import Chapter2 from "@/components/Chapter2";

export default {
  components: {
    Prolog,
    Chapter1,
    Chapter2
  },
  methods: {
    nextStep: function() {
      this.e1 = +this.e1;
      if (this.e1 < 3) {
        this.e1 = this.e1 + 1;
      }
    },
  },
  data: () => ({
    e1: 0
  })
};
</script>

<style>
</style>
