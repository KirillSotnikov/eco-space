<template>
  <v-container fluid>
    <h1 class="teachers-title">{{title}}</h1>
    <v-row>
      <v-col
        cols="12"
        sm="4"
        v-for="(teacher, n) in teachers"
        :key="n"
      >
        <v-card
          class=""
          tile
        >
          <v-img
            height="100%"
            :src="teacher.backgroundUrl"
          >
            <v-row
              align="end"
              class="fill-height"
            >
              <v-col
                align-self="start"
                class="pa-0"
                cols="12"
              >
                <v-avatar
                  class="profile"
                  color="grey"
                  size="164"
                  tile
                >
                  <v-img :src="teacher.url"></v-img>
                </v-avatar>
              </v-col>
              <v-col class="py-0">
                <v-list-item
                  color="rgba(0, 0, 0, .4)"
                  dark
                >
                  <v-list-item-content>
                    <v-list-item-title class="title">{{teacher.firstName}} {{teacher.secondName}}</v-list-item-title>
                    <v-list-item-subtitle>{{teacher.duty}}</v-list-item-subtitle>
                  </v-list-item-content>
                </v-list-item>
              </v-col>
            </v-row>
          </v-img>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  props: [
    'teachers',
    'title'
  ]
}
</script>

<style lang="scss" scoped>
  .teachers-title{
    margin-bottom: 20px;
  }
</style>
