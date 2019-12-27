<template>
  <app-account-marks :title="`Marks of user-${pageId}`" />
</template>

<script>
import accountMarks from '@/components/accountPage/accountMarks.vue'
export default {
  components: {
    'app-account-marks': accountMarks
  },
  asyncData ({ params }) {
    return {
      pageId: params.id
    }
  }
}
</script>
