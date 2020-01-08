<template>
  <v-container fluid>
    <h1 class="news-title">News</h1>
    <v-row>
      <v-col cols="12" md="6" lg="4" v-for="n in count" :key="n">
        <v-card>
          <v-list-item>
            <v-list-item-avatar color="grey"><v-img src="https://cdn.vuetifyjs.com/images/lists/1.jpg"/></v-list-item-avatar>
            <v-list-item-content>
              <v-list-item-title class="headline">Our Changing Planet</v-list-item-title>
              <v-list-item-subtitle>by Kurt Wagner</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>

          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/mountain.jpg"
            height="194"
          ></v-img>

          <v-card-text>
            Visit ten places on our planet that are undergoing the biggest changes today.
          </v-card-text>

          <v-card-actions>
            <v-btn
              text
              color="orange"
              :to="`/news/${n}`"
            >
              Read
            </v-btn>
            <v-spacer></v-spacer>
            <v-btn icon>
              <v-icon>mdi-heart</v-icon>
            </v-btn>
            <!-- <v-btn icon>
              <v-icon>mdi-share-variant</v-icon>
            </v-btn> -->
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
    <div class="d-flex justify-center">
      <v-btn class="ma-2" tile outlined color="grey lighten-1" @click="readMore">
        More news <v-icon right>mdi-chevron-down</v-icon>
      </v-btn>
    </div>
  </v-container>
</template>

<script>
export default {
  data () {
    return {
      count: 6
    }
  },
  methods: {
    readMore () {
      this.count += 3
    }
  }
}
</script>

<style lang="scss" scoped>
.news-title{
  margin-top: 20px;
  margin-bottom: 20px;
}
</style>
