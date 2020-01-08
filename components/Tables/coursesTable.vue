<template>
<v-container fluid>

  <v-data-table
    :headers="headers"
    :items="desserts"
    class="elevation-1 px-2"
    :items-per-page="5"
  >
    <template v-slot:item.actions="{ item }">
      <v-btn
        :to="`/courses/${item.actions}`"
        class="ma-2"
        outlined
        small
        fab
        color="green accent-2"
      >
        <v-icon>mdi-page-next-outline</v-icon>
      </v-btn>
      <v-btn
        :to="`/courses/edit/${item.name}`"
        class="ma-2"
        outlined
        small
        fab
        color="yellow accent-2"
      >
        <v-icon>mdi-pencil-outline</v-icon>
      </v-btn>
      <v-btn
        class="ma-2"
        outlined
        small
        fab
        color="red accent-2"
        @click="openDialog(item.name)"
      >
        <v-icon>mdi-delete-outline</v-icon>
      </v-btn>
    </template>
  </v-data-table>
  <app-group-delete-dialog
    firstColor="red darken-1"
    secondColor="green darken-1"
    :closeMethod="closeDialog"
    :isActive="isActiveDialog"
    :name="groupName"
    title="Are you sure?"
    :description="`Do you want to delete ${groupName}?`" />
</v-container>
</template>

<script>
import groupDeleteDialog from '@/components/Dialogs/groupDeleteDialog.vue'
export default {
  components: {
    'app-group-delete-dialog': groupDeleteDialog
  },
  data () {
    return {
      groupName: '',
      isActiveDialog: false,
      headers: [
        {
          text: 'Courses name',
          align: 'left',
          sortable: true,
          value: 'name'
        },
        {
          text: 'Actions',
          value: 'actions',
          sortable: false,
          align: 'right'
        }
      ],
      desserts: [
        {
          name: 'Math',
          actions: 1
        },
        {
          name: 'English',
          actions: 2
        },
        {
          name: 'Biology',
          actions: 3
        },
        {
          name: 'Biology',
          actions: 4
        },
        {
          name: 'Physics',
          actions: 5
        },
        {
          name: 'History',
          actions: 6
        },
        {
          name: 'HTML + CSS',
          actions: 7
        },
        {
          name: 'JavaScript',
          actions: 8
        },
        {
          name: 'Guitar',
          actions: 9
        },
        {
          name: 'Piano',
          actions: 10
        }
      ]
    }
  },
  methods: {
    openDialog (name) {
      this.isActiveDialog = true
      this.groupName = name
    },
    closeDialog () {
      this.isActiveDialog = false
      this.groupName = ''
    }
  }
}
</script>
