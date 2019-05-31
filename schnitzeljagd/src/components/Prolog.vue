<template>
  <v-flex xs6 offset-xs3>
    <v-layout justify-center>
      <v-card flat max-width="400">
        <v-card-title>
          <h2 class="headline">Prolog</h2>
        </v-card-title>
        <v-card-text>{{ prolog }}</v-card-text>
        <v-card-text>{{ prolog2 }}</v-card-text>
        <v-card-actions>
          <v-btn flat color="orange" @click="nextStep">>> Weiter zu Kapitel 1</v-btn>
        </v-card-actions>
      </v-card>
    </v-layout>
  </v-flex>
</template>

<script>
export default {
    props: ['nextStep'],
  data: () => ({
    prolog:
      "Eines Tages schlenderte ich über den Markt von Republika als ich auf einem Stand ein abgenutztes Buch entdeckte. Es war nicht die schlechte Art von abgenutzt, " +
      'sondern so als hätte es schon viele Abenteuer mitgemacht. Ich schaute es mir genauer an: "Das Tagebuch von Walter dem Wasserbändiger" ',
    prolog2:
      '"Walter der Wasserbändiger?" dachte ich. Das war doch dieser alte Kauz aus unserem Dorf. Er erzählte immer Geschichten von seinen Abenteuern und das er das größte ' +
      "Geheimnis von Republika entdeckt hatte. Aber die Leute glaubten ihm nicht und hielten ihn für verrückt. Immer wenn er anfing zu erzählen riefen Sie " +
      '"Alter Walter! Nicht die Geschichte schon wieder!" und lachten. Vor ein paar Jahren verschwand er dann spurlos...'
  })
};
</script>

<style>
</style>
