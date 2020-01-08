<template>
  <v-container>
    <h1 class="mb-7">Create new group</h1>
    <app-group-form
      :isSuperadmin="isSuperadmin"
      :teacherName="teacher"
      :teachers="teachers"
      :dates="dates"
      :pupils="pupils"
      :people="people"
      btnText="Create"
      btnIcon="mdi-plus"
    />
  </v-container>
</template>

<script>
import groupForm from '@/components/Forms/groupForm.vue'

const srcs = {
  1: 'https://cdn.vuetifyjs.com/images/lists/1.jpg',
  2: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
  3: 'https://cdn.vuetifyjs.com/images/lists/3.jpg',
  4: 'https://cdn.vuetifyjs.com/images/lists/4.jpg',
  5: 'https://cdn.vuetifyjs.com/images/lists/5.jpg'
}
export default {
  components: {
    'app-group-form': groupForm
  },
  data () {
    return {
      isSuperadmin: true,
      teacher: '',
      teachers: [
        'Vadim Parhomenko',
        'Kostya Parhomenko',
        'Kyryll Sotnykov',
        'Vadim Dubrovskiy',
        'Oleg Dyachenko',
        'Dima Pchelyanskiy'
      ],
      dates: [new Date().toISOString().substr(0, 10)],
      pupils: [],
      people: [
        { name: 'Sandra Adams', group: 'Group 1', avatar: srcs[1], id: 1 },
        { name: 'Ali Connors', group: 'Group 1', avatar: srcs[2], id: 2 },
        { name: 'Trevor Hansen', group: 'Group 1', avatar: srcs[3], id: 3 },
        { name: 'Tucker Smith', group: 'Group 1', avatar: srcs[2], id: 4 },
        { name: 'Britta Holt', group: 'Group 2', avatar: srcs[4], id: 5 },
        { name: 'Jane Smith ', group: 'Group 2', avatar: srcs[5], id: 6 },
        { name: 'John Smith', group: 'Group 2', avatar: srcs[1], id: 7 },
        { name: 'Sandra Williams', group: 'Group 2', avatar: srcs[3], id: 8 }
      ]
    }
  }
}
</script>
