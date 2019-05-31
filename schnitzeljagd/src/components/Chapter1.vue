<template>
  <v-flex xs8 offset-xs2>
    <v-layout justify-center>
      <v-card flat max-width="400">
        <v-card-title>
          <h2 class="headline">Kapitel 1</h2>
        </v-card-title>
        <v-card-text>{{ date1 }}</v-card-text>
        <v-card-text>{{ kapitel1 }}</v-card-text>
        <v-card-text>
          <v-layout align-center column>
            <v-list>
              <v-list-tile v-for="(q, key) in quest1" v-bind:key="key">
                <i>{{ q }}</i>
              </v-list-tile>
            </v-list>
          </v-layout>
        </v-card-text>
        <v-card-actions>
          <v-text-field
            label="Antwort"
            :success="answered"
            clearable
            :validate-on-blur="true"
            :rules="[validate]"
          ></v-text-field>
        </v-card-actions>
        <v-card-actions>
          <v-btn :disabled="!answered" flat color="orange" @click="nextStep">>> Weiter zu Kapitel 2</v-btn>
        </v-card-actions>
      </v-card>
    </v-layout>
  </v-flex>
</template>

<script>
export default {
  props: ["nextStep"],
  data: () => ({
    answered: false,
    date1: "21.02.2016",
    kapitel1:
      "Liebes Tagebuch, heute beginnt mein großes Abenteuer. Ich werde das große Geheimnis von Republika lösen, das Vermächtnis des ersten Avatar's. " +
      'Meine Reise startet auf dem Marktplatz von Republika. Zusammen mit meinem treuen Pferd "Wölkchen" breche ich nach Westen auf. Nach kurzer Zeit komme ' +
      "ich an eine Wegkreuzung. Dort wartet bereits ein Hase auf mich und er wiederholt stehts dasselbe Gedicht:",
    quest1: [
      "bla blub bla blub",
      "die franzi ist doof",
      "der Kero muss schreiben",
      "noch dieses Gedicht",
      'also antworte einfach "ja"'
    ]
  }),
  methods: {
    validate: function(input) {
      if (atob(input) == "\u008d") {
        this.answered = true;
        return true;
      } else {
        return "Falsche Antwort!";
      }
    }
  }
};
</script>

<style>
</style>
