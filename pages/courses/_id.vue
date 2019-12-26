<template>
  <div>
    <app-first-image title="Geography" subtitle="Build your application today!" />
    <v-row>
      <v-col col-12 md="12">
        <app-teacher-section title="Our teachers" :teachers="teachers"/>
      </v-col>
      <v-col col-12 md="12">
        <app-advantages :advantages="advantages" title="Course advantages" />
      </v-col>
      <app-reviews-list title="Course reviews" :count="count" />
    </v-row>
  </div>
</template>

<script>
import advantages from '@/components/coursePage/advantages.vue'
import firstImage from '@/components/coursePage/firstImage.vue'
import teacherSection from '@/components/coursePage/teacherSection.vue'
import reviewsList from '@/components/coursePage/reviewsList.vue'
export default {
  validate ({ params }) {
    return /^\d+$/.test(params.id)
  },
  components: {
    'app-advantages': advantages,
    'app-first-image': firstImage,
    'app-teacher-section': teacherSection,
    'app-reviews-list': reviewsList
  },
  asyncData ({ params }) {
    return {
      pageId: params.id
      // pageId: params.id
    }
  },
  data () {
    return {
      count: 3,
      advantages: [
        {
          title: 'Advantage 1',
          description: 'Tab 1 text. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
        },
        {
          title: 'Advantage 2',
          description: 'Tab 2 text. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
        },
        {
          title: 'Advantage 3',
          description: 'Tab 3 text. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
        },
        {
          title: 'Advantage 4',
          description: 'Tab 4 text. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
        }
      ],
      teachers: [
        {
          url: 'https://cdn.vuetifyjs.com/images/profiles/marcus.jpg',
          firstName: 'Marcus',
          secondName: 'Pitt',
          duty: 'Director',
          backgroundUrl: 'https://i.picsum.photos/id/961/510/300.jpg'
        },
        {
          url: 'https://cdn.vuetifyjs.com/images/john.jpg',
          firstName: 'John',
          secondName: 'Obrien',
          duty: 'Engineer',
          backgroundUrl: 'https://i.picsum.photos/id/962/510/300.jpg'
        },
        {
          url: 'https://cdn.vuetifyjs.com/images/lists/1.jpg',
          firstName: 'Oleg',
          secondName: 'Roberts',
          duty: 'Teacher',
          backgroundUrl: 'https://i.picsum.photos/id/1019/510/300.jpg'
        }
      ]
    }
  }
}
</script>
