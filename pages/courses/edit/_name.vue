<template>
  <v-container fluid>
    <h1 class="mb-7">Edit - {{courseName}}</h1>
    <app-courses-form :startCourseDate="startCourseDate" :courseDescription="courseDescription" />
  </v-container>
</template>

<script>
import courseForm from '@/components/coursePage/Form/coursesForm.vue'
export default {
  asyncData ({ params }) {
    return {
      courseName: params.name
    }
  },
  data () {
    return {
      startCourseDate: new Date().toISOString().substr(0, 10),
      courseDescription: ''
    }
  },
  components: {
    'app-courses-form': courseForm
  }
}
</script>
