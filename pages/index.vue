
<template>
  <div>
    <app-slider />
    <app-card-list />
  </div>
</template>

<script>

import Slider from '@/components/MainPage/Slider'
import CardList from '@/components/MainPage/CardList'

export default {
  components: {
    'app-slider': Slider,
    'app-card-list': CardList
  },
  data () {
    return {
      testData: 'Text'
    }
  }
}

</script>
