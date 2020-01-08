<template>
  <app-account-marks :title="`Marks of user - ${userId}`" />
</template>

<script>
import accountMarks from '@/components/accountPage/accountMarks.vue'
export default {
  components: {
    'app-account-marks': accountMarks
  },
  asyncData ({ query }) {
    return {
      userId: query.userId
    }
  }
}
</script>
