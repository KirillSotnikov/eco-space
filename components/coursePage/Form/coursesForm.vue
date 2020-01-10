<template>
  <form>
    <v-row>
      <v-col cols="12" md="6">
        <p>Starting course</p>
        <v-date-picker full-width landscape color="blue" :min="minDate" v-model="startCourseDate"></v-date-picker>
      </v-col>
      <v-col cols="12" md="6">
        <p>Course description</p>
        <v-textarea
          outlined
          name="input-7-4"
          v-model="courseDescription"
          clearable
          no-resize
          :rows="10"
        ></v-textarea>
      </v-col>
      <v-col cols="12" md="6">
        <v-text-field
            label="Courses duration"
            outlined
            v-model="coursesDuration"
          ></v-text-field>
      </v-col>
      <v-col cols="12" md="6">
        <v-autocomplete
          v-model="selectedTeachers"
          :items="teachers"
          filled
          chips
          color="blue-grey lighten-2"
          label="Teachers"
          item-text="name"
          item-value="name"
          multiple
          outlined
          dense
          class="teachers-select"
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
      <v-col cols="12">
        <v-card class="pa-5">
          <div class="my-2 d-flex align-items-center justify-space-between">
            <h3>Advantages</h3>
            <v-btn color="blue" small fab dark @click="addAdvantage">
              <v-icon>mdi-plus</v-icon>
            </v-btn>
          </div>
          <v-row
            v-for="(advantage, index) in advantages"
            :key="index">
            <v-col class="d-flex" cols="12" md="6">
              <v-btn
                class="mr-5"
                color="red"
                small
                fab
                dark
                @click="deleteAdvantage(index)"
              >
                <v-icon>mdi-delete</v-icon>
              </v-btn>
              <v-text-field
                label="Advantage title"
                outlined
                v-model="advantage.title"
              ></v-text-field>
            </v-col>
            <v-col>
              <v-textarea
                outlined
                name="input-7-4"
                clearable
                no-resize
                :rows="5"
                label="Advantage description"
                v-model="advantage.description"
              ></v-textarea>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>
    <v-btn class="ma-2" tile outlined color="success">
      <v-icon left>{{btnIcon}}</v-icon>
      {{btnText}}
    </v-btn>
  </form>
</template>

<script>
export default {
  props: [
    'startCourseDate',
    'courseDescription',
    'teachers',
    'selectedTeachers',
    'advantages',
    'coursesDuration',
    'btnIcon',
    'btnText'
  ],
  data () {
    return {
      minDate: new Date().toISOString().substr(0, 10)
    }
  },
  methods: {
    remove (item) {
      const index = this.selectedTeachers.indexOf(item.name)
      if (index >= 0) { this.selectedTeachers.splice(index, 1) }
    },
    goTo (id) {
      const userUrl = `http://localhost:3000/users/${id}`
      window.open(userUrl, '_blank')
    },
    addAdvantage () {
      const advantageTemplate = {
        title: '',
        description: ''
      }
      this.advantages.push(advantageTemplate)
    },
    deleteAdvantage (index) {
      this.advantages.splice(index, 1)
    }
  }
}
</script>

<style lang="scss">
.teachers-select{
  .v-select__slot{
    height: 56px;
  }
}
</style>
