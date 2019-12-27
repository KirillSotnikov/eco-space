<template>
  <v-container fluid>
    <h2 class="reviews-title">{{title}}</h2>
    <v-row>
      <v-col cols="12" md="4" v-for="n in reviewsCount" :key="n">
        <v-card
          color="grey darken-3"
          dark
        >
          <v-card-title>
            <v-icon
              large
              left
            >
              mdi-compass
            </v-icon>
            <span class="title font-weight-light">Eco Space</span>
          </v-card-title>

          <v-card-text class="headline font-weight-bold">
            "Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well."
          </v-card-text>

          <v-card-actions>
            <v-list-item class="grow">
              <v-list-item-avatar color="grey darken-3">
                <v-img
                  class="elevation-6"
                  src="https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&accessoriesType=Prescription02&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=White&eyeType=Default&eyebrowType=DefaultNatural&mouthType=Default&skinColor=Light"
                ></v-img>
              </v-list-item-avatar>

              <v-list-item-content>
                <v-list-item-title>Evan You</v-list-item-title>
              </v-list-item-content>

              <v-row
                align="center"
                justify="end"
              >
                <div>
                  <v-icon class="mr-1">mdi-heart</v-icon>
                  <span class="subheading mr-2">256</span>
                </div>
                <span class="mr-1">·</span>
                <div>
                  <v-icon class="mr-1">mdi-share-variant</v-icon>
                  <span class="subheading">45</span>
                </div>
              </v-row>
            </v-list-item>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
      <div class="d-flex justify-center">
        <v-btn class="ma-2" tile outlined color="grey lighten-1" @click="readMore">
          More reviews <v-icon right>mdi-chevron-down</v-icon>
        </v-btn>
      </div>
  </v-container>
</template>

<script>
export default {
  props: [
    'count',
    'title'
  ],
  data () {
    return {
      reviewsCount: this.count
    }
  },
  methods: {
    readMore () {
      this.reviewsCount += 3
    }
  }
}
</script>

<style lang="scss" scoped>
  .reviews-title{
    margin-bottom: 20px;
    margin-top: 20px;
  }
</style>
