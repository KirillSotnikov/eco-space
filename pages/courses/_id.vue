<template>
  <div>
    <app-first-image />
    <v-row>
      <v-col col-12 md="12">
        <app-teacher-section title="Our teachers" :teachers="teachers"/>
      </v-col>
      <v-col col-12 md="12">
        <app-advantages :advantages="advantages" title="Course advantages" />
      </v-col>
    </v-row>
  </div>
</template>

<script>
import advantages from '@/components/coursePage/advantages.vue'
import firstImage from '@/components/coursePage/firstImage.vue'
import teacherSection from '@/components/coursePage/teacherSection.vue'
export default {
  validate ({ params }) {
    return /^\d+$/.test(params.id)
  },
  components: {
    'app-advantages': advantages,
    'app-first-image': firstImage,
    'app-teacher-section': teacherSection
  },
  asyncData ({ params }) {
    return {
      pageId: params.id
      // pageId: params.id
    }
  },
  data () {
    return {
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
          duty: 'Director'
        },
        {
          url: 'https://cdn.vuetifyjs.com/images/john.jpg',
          firstName: 'John',
          secondName: 'Obrien',
          duty: 'Engineer'
        },
        {
          url: 'https://cdn.vuetifyjs.com/images/profiles/marcus.jpg',
          firstName: 'Marcus',
          secondName: 'Roberts',
          duty: 'Teacher'
        }
      ]
    }
  }
}
</script>
