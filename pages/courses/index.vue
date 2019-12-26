<template>
  <div>
    <h1 class="courses-title">Choose you course</h1>
    <v-tabs
      v-model="tab"
      background-color="grey darken-3"
      color="white"
      class="elevation-2"
      dark
      :centered="centered"
      :grow="grow"
      :vertical="vertical"
      :right="right"
      :prev-icon="prevIcon ? 'mdi-arrow-left-bold-box-outline' : undefined"
      :next-icon="nextIcon ? 'mdi-arrow-right-bold-box-outline' : undefined"
      :icons-and-text="icons"
    >
      <v-tabs-slider></v-tabs-slider>

      <v-tab
        v-for="(tab, i) in tabsValue"
        :key="i"
        :href="`#tab-${i}`"
      >
        {{tab.title}}
        <v-icon v-if="icons">mdi-phone</v-icon>
      </v-tab>

      <v-tab-item
        v-for="(tab, i) in tabsValue"
        :key="i"
        :value="'tab-' + i"
        class="tab-item"
      >
        <v-lazy>
          <app-card-list :subjects="tab.subjects" />
        </v-lazy>
      </v-tab-item>
    </v-tabs>
    <app-reviews-list title="Reviews list" :count="3" />
  </div>
</template>

<script>
import CardList from '@/components/MainPage/CardList.vue'
import reviewsList from '@/components/coursePage/reviewsList.vue'
export default {
  components: {
    'app-card-list': CardList,
    'app-reviews-list': reviewsList
  },
  data () {
    return {
      tab: null,
      text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
      icons: false,
      centered: false,
      grow: true,
      vertical: false,
      prevIcon: false,
      nextIcon: false,
      right: false,
      tabs: 3,
      tabsValue: [
        {
          title: 'Programming',
          text: 'Programming Text',
          subjects: [
            {
              url: 'https://cache.kwork.ru/pics/t3/16/178524-1.jpg',
              title: 'HTML + CSS',
              date: '02.02.2020',
              teacher: 'Whitehaven Beach',
              shortDescription: 'Whitsunday Island, Whitsunday Islands. Whitsunday Island, Whitsunday Islands. Whitsunday Island, Whitsunday Islands'
            },
            {
              url: 'https://img1.goodfon.ru/wallpaper/nbig/f/6d/geek-it-nerd-code-coding.jpg',
              title: 'JavaScript',
              date: '02.02.2020',
              teacher: 'Whitehaven Beach',
              shortDescription: 'Whitsunday Island, Whitsunday Islands. Whitsunday Island, Whitsunday Islands. Whitsunday Island, Whitsunday Islands'
            }
          ]
        },
        {
          title: 'ZNO',
          text: 'ZNO Text',
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
        },
        {
          title: 'Music',
          text: 'Music Text',
          subjects: [
            {
              url: 'https://ak0.picdn.net/shutterstock/videos/25552100/thumb/1.jpg',
              title: 'Guitar',
              date: '02.02.2020',
              teacher: 'Whitehaven Beach',
              shortDescription: 'Whitsunday Island, Whitsunday Islands. Whitsunday Island, Whitsunday Islands. Whitsunday Island, Whitsunday Islands'
            },
            {
              url: 'https://s1.funon.cc/img/orig/201802/05/5a782548b1d96.png',
              title: 'Piano',
              date: '02.02.2020',
              teacher: 'Whitehaven Beach',
              shortDescription: 'Whitsunday Island, Whitsunday Islands. Whitsunday Island, Whitsunday Islands. Whitsunday Island, Whitsunday Islands'
            }
          ]
        }
      ]
    }
  }
}
</script>

<style lang="scss">
.courses-title{
  margin-top: 20px;
  margin-bottom: 20px;
}
</style>
