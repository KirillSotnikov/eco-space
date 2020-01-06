<template>
  <v-container fluid>
    <h1 class="booking-title">Booking</h1>
    <div>
      <v-stepper v-model="e1">
        <v-stepper-header>
          <template v-for="n in steps">
            <v-stepper-step
              :key="`${n}-step`"
              :complete="e1 > n"
              :step="n"
              editable
            >
              Step {{ n }}
            </v-stepper-step>

            <v-divider
              v-if="n !== steps"
              :key="n"
            ></v-divider>
          </template>
        </v-stepper-header>

        <v-stepper-items>
          <v-stepper-content
            step="1"
          >
            <app-first-step :selectedCourse="selectedCourse" :coursesList="coursesList" :nextStep="nextStep" />
          </v-stepper-content>

          <v-stepper-content
            step="2"
          >
            <app-second-step :nextStep="nextStep" />
          </v-stepper-content>

          <v-stepper-content
            step="3"
          >
            <app-third-step :nextStep="nextStep" />
          </v-stepper-content>
        </v-stepper-items>
      </v-stepper>
    </div>
  </v-container>
</template>

<script>
import firstStep from '@/components/Booking/firstStep.vue'
import secondStep from '@/components/Booking/secondStep.vue'
import thirdStep from '@/components/Booking/thirdStep.vue'
export default {
  components: {
    'app-first-step': firstStep,
    'app-second-step': secondStep,
    'app-third-step': thirdStep
  },
  data () {
    return {
      e1: 1,
      steps: 3,
      selectedCourse: 'Geography',
      coursesList: [
        'Math',
        'English',
        'Biology',
        'Geography',
        'Physics',
        'History',
        'HTML + CSS',
        'JavaScript',
        'Guitar',
        'Piano'
      ]
    }
  },

  watch: {
    steps (val) {
      if (this.e1 > val) {
        this.e1 = val
      }
    }
  },

  methods: {
    nextStep (n) {
      this.e1 = n
    }
  }
}
</script>

<style lang="scss" scoped>
  .booking-title{
    margin-top: 20px;
    margin-bottom: 20px;
  }
</style>
