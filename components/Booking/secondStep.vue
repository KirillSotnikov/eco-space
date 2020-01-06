<template>
  <div>
    <v-card class="mb-12">
      <form class="pa-10">
        <h2>When we can call you?</h2>
        <v-row>
          <v-col cols="12" md="6">
            <v-date-picker
              class="mt-10"
              v-model="bookingDate"
              color="blue darken-2"
              :min="minDate"
              full-width
              landscape
            ></v-date-picker>
          </v-col>
          <v-col cols="12" md="6">
            <v-time-picker
              class="mt-10"
              color="blue darken-2"
              :allowed-hours="allowedHours"
              v-model="e7"
              format="24hr"
              full-width
              landscape
            ></v-time-picker>
          </v-col>
        </v-row>
      </form>
    </v-card>

    <v-btn
      color="primary"
      @click="nextStep(3)"
    >
      Continue
    </v-btn>

    <v-btn @click="nextStep(1)" text>Cancel</v-btn>
  </div>
</template>

<script>
export default {
  props: [
    'nextStep'
  ],
  data () {
    return {
      minDate: new Date().toISOString().substr(0, 10),
      bookingDate: new Date().toISOString().substr(0, 10),
      e7: '12:00'
    }
  },
  methods: {
    allowedHours: v => v !== 0 && v !== 1 && v !== 2 && v !== 3 && v !== 4 && v !== 5 && v !== 6 && v !== 7 && v !== 22 && v !== 23
  }
}
</script>
