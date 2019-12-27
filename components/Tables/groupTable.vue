<template>
  <v-data-table
    :headers="headers"
    :items="desserts"
    class="elevation-1 px-2"
  >
    <template v-slot:item.count="{ item }">
      <v-chip :color="getColor(item.count)" dark>{{ item.count }}</v-chip>
    </template>
    <template v-slot:item.actions="{ item }">
      <v-btn
        :to="`groups/${item.name}`"
        class="ma-2"
        outlined
        small
        fab
        color="green accent-2"
      >
        <v-icon>mdi-page-next-outline</v-icon>
      </v-btn>
      <v-btn
        :to="`groups/edit/${item.name}`"
        class="ma-2"
        outlined
        small
        fab
        color="yellow accent-2"
      >
        <v-icon>mdi-pencil-outline</v-icon>
      </v-btn>
      <v-btn
        :to="`groups/delete/${item.name}`"
        class="ma-2"
        outlined
        small
        fab
        color="red accent-2"
      >
        <v-icon>mdi-delete-outline</v-icon>
      </v-btn>
    </template>
  </v-data-table>
</template>

<script>
export default {
  data () {
    return {
      headers: [
        {
          text: 'Group name',
          align: 'left',
          sortable: false,
          value: 'name'
        },
        { text: 'Start Date', value: 'startDate' },
        { text: 'End Date', value: 'endDate' },
        { text: 'Progress', value: 'progress' },
        { text: 'Children count', value: 'count' },
        { text: 'Action', value: 'actions' }
      ],
      desserts: [
        {
          name: 'Math',
          count: 10,
          actions: 1,
          startDate: '02.10.2020',
          endDate: '02.10.2021',
          progress: '1%'
        },
        {
          name: 'English',
          count: 3,
          actions: 2,
          startDate: '02.10.2020',
          endDate: '02.10.2021',
          progress: '1%'
        },
        {
          name: 'Biology',
          count: 4,
          actions: 3,
          startDate: '02.10.2020',
          endDate: '02.10.2021',
          progress: '7%'
        },
        {
          name: 'Biology',
          count: 15,
          actions: 4,
          startDate: '02.10.2020',
          endDate: '02.10.2021',
          progress: '8%'
        },
        {
          name: 'Physics',
          count: 2,
          actions: 5,
          startDate: '02.10.2020',
          endDate: '02.10.2021',
          progress: '16%'
        },
        {
          name: 'History',
          count: 8,
          actions: 6,
          startDate: '02.10.2020',
          endDate: '02.10.2021',
          progress: '0%'
        },
        {
          name: 'HTML + CSS',
          count: 11,
          actions: 7,
          startDate: '02.10.2020',
          endDate: '02.10.2021',
          progress: '2%'
        },
        {
          name: 'JavaScript',
          count: 23,
          actions: 8,
          startDate: '02.10.2020',
          endDate: '02.10.2021',
          progress: '45%'
        },
        {
          name: 'Guitar',
          count: 13,
          actions: 9,
          startDate: '02.10.2020',
          endDate: '02.10.2021',
          progress: '22%'
        },
        {
          name: 'Piano',
          count: 5,
          actions: 10,
          startDate: '02.10.2020',
          endDate: '02.10.2021',
          progress: '6%'
        }
      ]
    }
  },
  methods: {
    getColor (calories) {
      if (calories > 15) {
        return 'green'
      } else if (calories > 8) {
        return 'orange'
      } else {
        return 'red'
      }
    }
  }
}
</script>
