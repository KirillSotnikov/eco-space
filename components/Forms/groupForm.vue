<template>
  <div>
    <form action="">
      <v-row>
        <v-col cols="12" sm="6">
          <v-text-field
            label="Group name"
            outlined
            dense
            v-model="groupName"
          ></v-text-field>
        </v-col>
        <v-col cols="12" sm="6">
          <v-autocomplete
            label="Teacher"
            outlined
            dense
            v-model="teacherName"
            :disabled="!isSuperadmin"
            item-color="white"
            :items="teachers"
          ></v-autocomplete>
        </v-col>
        <v-col cols="12" sm="6">
          <v-date-picker
            color="blue darken-2"
            :min="minDate"
            v-model="dates"
            range
            full-width
          ></v-date-picker>
        </v-col>
        <v-col cols="12" sm="6">
          <v-text-field v-model="dateRangeText" label="Date range" readonly></v-text-field>
        </v-col>
         <v-col cols="12">
          <v-autocomplete
            v-model="pupils"
            :items="people"
            filled
            chips
            color="blue-grey lighten-2"
            label="Pupils"
            item-text="name"
            item-value="name"
            multiple
            outlined
            dense
          >
            <template v-slot:selection="data">
              <v-chip
                v-bind="data.attrs"
                :input-value="data.selected"
                close
                @click="goTo(data.item.id)"
                @click:close="remove(data.item)"
              >
                <v-avatar left>
                  <v-img :src="data.item.avatar"></v-img>
                </v-avatar>
                {{ data.item.name }}
              </v-chip>
            </template>
            <template v-slot:item="data">
              <template v-if="typeof data.item !== 'object'">
                <v-list-item-content v-text="data.item"></v-list-item-content>
              </template>
              <template v-else>
                <v-list-item-avatar>
                  <img :src="data.item.avatar">
                </v-list-item-avatar>
                <v-list-item-content>
                  <v-list-item-title v-html="data.item.name"></v-list-item-title>
                  <v-list-item-subtitle v-html="data.item.group"></v-list-item-subtitle>
                </v-list-item-content>
              </template>
            </template>
          </v-autocomplete>
        </v-col>
      </v-row>
      <v-btn class="ma-2" tile outlined color="success">
        <v-icon left>{{btnIcon}}</v-icon>
        {{btnText}}
      </v-btn>
    </form>
  </div>
</template>

<script>
export default {
  props: [
    'groupName',
    'teacherName',
    'teachers',
    'dates',
    'isSuperadmin',
    'pupils',
    'people',
    'btnText',
    'btnEdit',
    'btnIcon'
  ],
  data: () => ({
    minDate: new Date().toISOString().substr(0, 10),
    select: []
  }),
  computed: {
    dateRangeText () {
      return this.dates.join(' ~ ')
    }
  },
  methods: {
    remove (item) {
      const index = this.pupils.indexOf(item.name)
      if (index >= 0) { this.pupils.splice(index, 1) }
    },
    goTo (id) {
      const userUrl = `http://localhost:3000/users/${id}`
      window.open(userUrl, '_blank')
    }
  }
}
</script>
