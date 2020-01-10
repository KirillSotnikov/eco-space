<template>
  <v-container fluid>
    <div class="d-flex justify-space-between mb-5">
      <h1 class="groups-title">Courses list</h1>
      <v-btn
        :class="{ active: isActive }"
        class="booking-course"
        color="grey darken-3"
        @mouseover="isActive = true"
        @mouseleave="isActive = false"
        dark
        to="/courses/add"
      >
        <p class="booking-course__text">New course</p>
        <v-icon>mdi-plus</v-icon>
      </v-btn>
    </div>
    <app-courses-table />
  </v-container>
</template>

<script>
import coursesTable from '@/components/Tables/coursesTable.vue'
export default {
  components: {
    'app-courses-table': coursesTable
  },
  data () {
    return {
      isActive: false
    }
  }
}
</script>

<style lang="scss" scoped>
.booking-course{
  border-radius: 100%;
    border-radius: 30px;
  display: flex;
  align-items: center;
  transition: all .4s ease-out;
  padding: 5px 10px !important;
  min-width: unset !important;
  height: 44px !important;
  &.active{
    border-radius: 30px;
    .booking-course__text{
      margin-right: 10px;
      width: 100px;
    }
  }
  &__text{
    margin-bottom: 0;
    width: 0;
    overflow: hidden;
    margin-right: 0;
    transition: all .4s ease-out .1s;
  }
}
</style>
