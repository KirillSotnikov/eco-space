<template>
  <v-container>
    <h1 class="mb-7">Edit - {{courseName}}</h1>
    <app-courses-form
      :startCourseDate="startCourseDate"
      :courseDescription="courseDescription"
      :teachers="teachers"
      :selectedTeachers="selectedTeachers"
      :advantages="advantages"
      :coursesDuration="coursesDuration"
      btnText="Edit"
      btnIcon="mdi-pencil"
    />
  </v-container>
</template>

<script>
import courseForm from '@/components/coursePage/Form/coursesForm.vue'

const srcs = {
  1: 'https://cdn.vuetifyjs.com/images/lists/1.jpg',
  2: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
  3: 'https://cdn.vuetifyjs.com/images/lists/3.jpg',
  4: 'https://cdn.vuetifyjs.com/images/lists/4.jpg',
  5: 'https://cdn.vuetifyjs.com/images/lists/5.jpg'
}
export default {
  asyncData ({ params }) {
    return {
      courseName: params.name
    }
  },
  data () {
    return {
      coursesDuration: '2 monthes',
      startCourseDate: new Date().toISOString().substr(0, 10),
      courseDescription: 'Lorem ipsum dolor sit amet consectetur, adipisicing elit. Consequatur optio culpa placeat adipisci rem vero expedita autem, animi assumenda praesentium eum perspiciatis pariatur? Vero hic necessitatibus et eum aliquid qui!',
      selectedTeachers: ['Sandra Adams', 'Britta Holt'],
      teachers: [
        { name: 'Sandra Adams', group: 'Group 1', avatar: srcs[1], id: 1 },
        { name: 'Ali Connors', group: 'Group 1', avatar: srcs[2], id: 2 },
        { name: 'Trevor Hansen', group: 'Group 1', avatar: srcs[3], id: 3 },
        { name: 'Tucker Smith', group: 'Group 1', avatar: srcs[2], id: 4 },
        { name: 'Britta Holt', group: 'Group 2', avatar: srcs[4], id: 5 },
        { name: 'Jane Smith ', group: 'Group 2', avatar: srcs[5], id: 6 },
        { name: 'John Smith', group: 'Group 2', avatar: srcs[1], id: 7 },
        { name: 'Sandra Williams', group: 'Group 2', avatar: srcs[3], id: 8 }
      ],
      advantages: [
        {
          title: 'Advantage 1',
          description: 'Advantage description 1'
        },
        {
          title: 'Advantage 2',
          description: 'Advantage description 1'
        },
        {
          title: 'Advantage 3',
          description: 'Advantage description 1'
        }
      ]
    }
  },
  components: {
    'app-courses-form': courseForm
  }
}
</script>
