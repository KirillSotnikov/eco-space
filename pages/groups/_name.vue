<template>
  <v-container>
    <h1>Group - {{pageId}}</h1>
    <app-children-list :group="pageId" :children="children" />
  </v-container>
</template>

<script>
import childrenList from '@/components/groupsPage/childrenList'
export default {
  asyncData ({ params }) {
    return {
      pageId: params.name
      // pageId: params.id
    }
  },
  components: {
    'app-children-list': childrenList
  },
  data () {
    return {
      children: [
        {
          id: 1,
          firstName: 'John',
          secondName: 'Nickols',
          shortDescription: 'Greyhound divisely hello coldly fonwderfully'
        },
        {
          id: 2,
          firstName: 'Dave',
          secondName: 'Nickols',
          shortDescription: 'Greyhound divisely hello coldly fonwderfully'
        },
        {
          id: 3,
          firstName: 'Oleg',
          secondName: 'Nickols',
          shortDescription: 'Greyhound divisely hello coldly fonwderfully'
        },
        {
          id: 4,
          firstName: 'Dordon',
          secondName: 'Nickols',
          shortDescription: 'Greyhound divisely hello coldly fonwderfully'
        }
      ]
    }
  }
}
</script>
