<template>
  <div>
    <h2 class="gallery-title">Our gallery</h2>
    <v-slide-group
      v-model="model"
      class="pa-0"
      active-class="success"
      show-arrows
    >
      <v-slide-item
        v-for="(item, n) in gallery"
        :key="n"
        v-slot:default="{ active, toggle }"
      >
        <v-card
          :color="active ? undefined : 'grey lighten-1'"
          class="ma-2"
          height="300"
          width="300px"
          @click="toggle"
        >
          <v-img style="margin-bottom: 20px;" height="300" :src="item.url" aspect-ratio="1.7"></v-img>
        </v-card>
      </v-slide-item>
    </v-slide-group>
  </div>
</template>

<script>
export default {
  data: () => ({
    model: null,
    gallery: [
      {
        url: 'https://i.picsum.photos/id/961/510/300.jpg'
      },
      {
        url: 'https://i.picsum.photos/id/962/510/300.jpg'
      },
      {
        url: 'https://i.picsum.photos/id/1019/510/300.jpg'
      },
      {
        url: 'https://i.picsum.photos/id/964/510/300.jpg'
      },
      {
        url: 'https://i.picsum.photos/id/965/510/300.jpg'
      },
      {
        url: 'https://i.picsum.photos/id/966/510/300.jpg'
      },
      {
        url: 'https://i.picsum.photos/id/1011/510/300.jpg'
      },
      {
        url: 'https://i.picsum.photos/id/1012/510/300.jpg'
      },
      {
        url: 'https://i.picsum.photos/id/1013/510/300.jpg'
      }
    ]
  })
}
</script>

<style lang="scss" scoped>
  .gallery-title{
    margin-top: 20px;
    margin-bottom: 20px;
  }
</style>
