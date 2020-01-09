<template>
  <v-row>
    <v-col cols="12" md="6">
      <p>Starting course</p>
      <v-date-picker full-width landscape color="blue" :min="minDate" v-model="startCourseDate"></v-date-picker>
    </v-col>
    <v-col cols="12" md="6">
      <v-textarea
        outlined
        name="input-7-4"
        label="Course description"
        v-model="courseDescription"
      ></v-textarea>
    </v-col>
  </v-row>
</template>

<script>
export default {
  props: [
    'startCourseDate',
    'courseDescription'
  ],
  data () {
    return {
      minDate: new Date().toISOString().substr(0, 10)
    }
  }
}
</script>
