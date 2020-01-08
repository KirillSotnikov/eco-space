<template>
  <v-container fluid>
    <h1>Courses list</h1>
    <app-courses-table />
  </v-container>
</template>

<script>
import coursesTable from '@/components/Tables/coursesTable.vue'
export default {
  components: {
    'app-courses-table': coursesTable
  }
}
</script>
