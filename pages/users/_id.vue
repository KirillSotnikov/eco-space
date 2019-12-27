<template>
  <v-container fluid>
    <app-account-info :title="`John Obrien ${pageId}`" />
    <app-courses-list :title="`Courses ${pageId}`" :courses="courses"/>
    <app-reviews-list :title="`Reviews ${pageId}`" :count="3"/>
  </v-container>
</template>

<script>
import coursesList from '@/components/accountPage/coursesList.vue'
import reviewsList from '@/components/coursePage/reviewsList.vue'
import accountInfo from '@/components/accountPage/accountInfo.vue'
export default {
  components: {
    'app-courses-list': coursesList,
    'app-reviews-list': reviewsList,
    'app-account-info': accountInfo
  },
  asyncData ({ params }) {
    return {
      pageId: params.id
      // pageId: params.id
    }
  },
  data: () => ({
    courses: [
      {
        color: '#1F7087',
        src: 'https://cdn.vuetifyjs.com/images/cards/foster.jpg',
        title: 'Math',
        artist: 'Foster the People'
      },
      {
        color: '#952175',
        src: 'https://cdn.vuetifyjs.com/images/cards/halcyon.png',
        title: 'English',
        artist: 'Ellie Goulding'
      },
      {
        color: '#1F7087',
        src: 'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg',
        title: 'Biology',
        artist: 'Foster the People'
      },
      {
        color: '#952175',
        src: 'https://cdn.vuetifyjs.com/images/cards/cooking.png',
        title: 'Guitar',
        artist: 'Ellie Goulding'
      },
      {
        color: '#1F7087',
        src: 'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg',
        title: 'Piano',
        artist: 'Foster the People'
      },
      {
        color: '#952175',
        src: 'https://cdn.vuetifyjs.com/images/cards/cooking.png',
        title: 'Physics',
        artist: 'Ellie Goulding'
      }
    ]
  })
}
</script>
