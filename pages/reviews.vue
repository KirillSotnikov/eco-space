<template>
  <v-container fluid>
    <app-reviews-form v-if="isAuthorised" />
    <app-reviews-list title="Reviews about us" :count="count" />
  </v-container>
</template>

<script>
import reviewsList from '@/components/coursePage/reviewsList.vue'
import reviewsForm from '@/components/reviewsPage/reviewsForm.vue'
export default {
  components: {
    'app-reviews-list': reviewsList,
    'app-reviews-form': reviewsForm
  },
  data () {
    return {
      isAuthorised: true,
      count: 6
    }
  }
}
</script>
