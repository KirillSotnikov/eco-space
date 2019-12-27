<template>
  <v-row dense>
      <v-col cols="12">
        <h2 class="courses-title">{{title}}</h2>
      </v-col>
      <v-col
        v-for="(item, i) in courses"
        :key="i"
        cols="12"
        md="4"
      >
        <v-card
          :color="item.color"
          dark
        >
          <div class="d-flex flex-no-wrap justify-space-between">
            <div>
              <v-card-title
                class="headline"
                v-text="item.title"
              ></v-card-title>

              <v-card-subtitle v-text="item.artist"></v-card-subtitle>
            </div>

            <v-avatar
              class="ma-3"
              size="125"
              tile
            >
              <v-img :src="item.src"></v-img>
            </v-avatar>
          </div>
        </v-card>
      </v-col>
    </v-row>
</template>

<script>
export default {
  props: [
    'courses',
    'title'
  ]
}
</script>

<style lang="scss" scoped>
.courses-title{
  margin-top: 20px;
  margin-bottom: 20px;
}
</style>
