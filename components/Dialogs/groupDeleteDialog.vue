<template>
  <v-row justify="center">
    <v-dialog v-model="isActive" persistent max-width="290">
      <v-card>
        <v-card-title class="headline">{{title}}</v-card-title>
        <v-card-text>{{description}}</v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn :color="firstColor" text @click="closeMethod">Disagree</v-btn>
          <v-btn :color="secondColor" text @click="closeMethod">Agree</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
</template>

<script>
export default {
  props: [
    'id',
    'title',
    'description',
    'isActive',
    'closeMethod',
    'firstColor',
    'secondColor'
  ]
}
</script>
