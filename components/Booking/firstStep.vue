<template>
  <div>
    <v-card class="mb-12" >
      <form class="pa-10">
        <h2>You want to book course?</h2>
        <h4>Well. Let's get it started!</h4>

        <div class="mt-10">
          <v-autocomplete
            v-model="selectedCourse"
            label="Which course do yopu want to book?"
            :items="coursesList"
          ></v-autocomplete>
        </div>
      </form>
    </v-card>

    <v-btn
      color="primary"
      @click="nextStep(2)"
    >
      Continue
    </v-btn>

    <v-btn to="/" text>Cancel booking</v-btn>
  </div>
</template>

<script>
export default {
  props: [
    'selectedCourse',
    'coursesList',
    'nextStep'
  ]
}
</script>
