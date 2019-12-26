<template>
<v-container fluid>
  <h1>About us</h1>
  <v-img style="margin-bottom: 20px;" height="300" src="https://i.picsum.photos/id/70/1920/1080.jpg" aspect-ratio="2"></v-img>
  <app-about-us />
  <app-about-gallery />
</v-container>
</template>

<script>
import aboutUs from '@/components/MainPage/aboutUs.vue'
import aboutUsGallery from '@/components/MainPage/aboutUsGallery.vue'
export default {
  components: {
    'app-about-us': aboutUs,
    'app-about-gallery': aboutUsGallery
  }
}
</script>
