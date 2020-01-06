<template>
  <div>
    <v-card class="mb-12"  >
      <form class="pa-10">
        <v-row>
          <v-col cols="12" md="6">
            <v-text-field label="Name" :rules="nameRules"></v-text-field>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field label="Email" type="email" :rules="emailRules"></v-text-field>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field label="Phone number" v-mask="'+38 (0##) ### ## ##'" type="tel" :rules="phoneRules"></v-text-field>
          </v-col>
        </v-row>
      </form>
    </v-card>

    <v-btn
      color="primary"
      :to="`/?snackbar=${snackbar}&snackbarText=${successText}&snackbarColor=${snackbarColor}`"
    >
      Book
    </v-btn>

    <v-btn @click="nextStep(2)" text>Cancel</v-btn>
  </div>
</template>

<script>
import { mask } from 'vue-the-mask'

export default {
  directives: { mask },
  props: [
    'nextStep'
  ],
  data () {
    return {
      snackbar: true,
      snackbarColor: 'green lighten-1',
      successText: 'Booking status - Success',
      nameRules: [
        value => !!value || 'Name is required.'
      ],
      phoneRules: [
        value => !!value || 'Phone is required.'
      ],
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+/.test(v) || 'E-mail must be valid'
      ]
    }
  }
}
</script>
