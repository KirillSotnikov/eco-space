
<template>
  <div>
    <app-slider />
    <app-card-list title="Popular courses" :subjects="subjects" />
    <app-about-gallery />
    <app-reviews-list title="Courses reviews" :count="3" />
  </div>
</template>

<script>

import Slider from '@/components/MainPage/Slider'
import CardList from '@/components/MainPage/CardList'
import reviewsList from '@/components/coursePage/reviewsList.vue'
import aboutUsGallery from '@/components/MainPage/aboutUsGallery.vue'

export default {
  components: {
    'app-slider': Slider,
    'app-card-list': CardList,
    'app-reviews-list': reviewsList,
    'app-about-gallery': aboutUsGallery
  },
  data () {
    return {
      testData: 'Text',
      subjects: [
        {
          url: 'https://usercontent2.hubstatic.com/14333385.jpg',
          title: 'Math',
          date: '02.02.2020',
          teacher: 'Whitehaven Beach',
          shortDescription: 'Whitsunday Island, Whitsunday Islands. Whitsunday Island, Whitsunday Islands. Whitsunday Island, Whitsunday Islands'
        },
        {
          url: 'https://previews.123rf.com/images/kbuntu/kbuntu1201/kbuntu120100005/11934653-dark-chalkboard-with-a-question-do-you-speak-english-.jpg',
          title: 'English',
          date: '02.02.2020',
          teacher: 'Whitehaven Beach',
          shortDescription: 'Whitsunday Island, Whitsunday Islands. Whitsunday Island, Whitsunday Islands. Whitsunday Island, Whitsunday Islands'
        },
        {
          url: 'https://miro.medium.com/max/852/1*bXEIfw00n_3ugHlibLGGPg.jpeg',
          title: 'Biology',
          date: '02.02.2020',
          teacher: 'Whitehaven Beach',
          shortDescription: 'Whitsunday Island, Whitsunday Islands. Whitsunday Island, Whitsunday Islands. Whitsunday Island, Whitsunday Islands'
        },
        {
          url: 'https://c4.wallpaperflare.com/wallpaper/965/216/980/world-map-dark-photoshopped-world-map-wallpaper-preview.jpg',
          title: 'Geography',
          date: '02.02.2020',
          teacher: 'Whitehaven Beach',
          shortDescription: 'Whitsunday Island, Whitsunday Islands. Whitsunday Island, Whitsunday Islands. Whitsunday Island, Whitsunday Islands'
        },
        {
          url: 'https://miro.medium.com/fit/c/1838/551/0*GjURUadCzayyT5Lb.jpg',
          title: 'Physics',
          date: '02.02.2020',
          teacher: 'Whitehaven Beach',
          shortDescription: 'Whitsunday Island, Whitsunday Islands. Whitsunday Island, Whitsunday Islands. Whitsunday Island, Whitsunday Islands'
        },
        {
          url: 'https://litreactor.com/sites/default/files/imagecache/header/images/column/headers/21741565422_0201bb9188_o.jpg',
          title: 'History',
          date: '02.02.2020',
          teacher: 'Whitehaven Beach',
          shortDescription: 'Whitsunday Island, Whitsunday Islands. Whitsunday Island, Whitsunday Islands. Whitsunday Island, Whitsunday Islands'
        }
      ]
    }
  }
}

</script>
