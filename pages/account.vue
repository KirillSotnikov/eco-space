<template>
  <div>
    <app-account-info :title="`John Obrien`" :duty="`Network Engineer`" />
  </div>
</template>

<script>
import accountInfo from '@/components/accountPage/accountInfo.vue'
export default {
  components: {
    'app-account-info': accountInfo
  }
}
</script>
