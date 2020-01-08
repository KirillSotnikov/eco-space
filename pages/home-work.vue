<template>
  <v-container fluid>
    <h1>Home work</h1>
    <v-timeline>
      <v-timeline-item
        v-for="(work, i) in homeWork"
        :key="i"
        :color="work.color"
        small
      >
        <template v-slot:opposite>
          <span
            :class="`headline font-weight-bold ${work.color}--text`"
            v-text="work.year"
          ></span>
        </template>
        <div class="py-4">
          <h2 :class="`headline font-weight-light mb-4 ${work.color}--text`">{{work.title}}</h2>
          <div>
            {{work.title}}.
            Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.
          </div>
          <v-btn
            :href="work.materialsLink"
            target="_blank"
            class="mt-2"
            tile
            outlined
            color="grey lighten-1"
          >
            Materials <v-icon right>mdi-download</v-icon>
          </v-btn>
        </div>
      </v-timeline-item>
    </v-timeline>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    homeWork: [
      {
        title: 'Make task 1',
        color: 'cyan',
        year: '02.12.1960',
        materialsLink: 'https://static.turbosquid.com/Preview/2019/06/18__05_46_22/00.jpg4091F190-46D5-4DB5-A304-FF1EEA07899FZoom.jpg'
      },
      {
        title: 'Make task 2',
        color: 'green',
        year: '02.12.1970',
        materialsLink: 'https://static.turbosquid.com/Preview/2019/06/18__05_46_22/00.jpg4091F190-46D5-4DB5-A304-FF1EEA07899FZoom.jpg'
      },
      {
        title: 'Make task 3',
        color: 'pink',
        year: '02.12.1980',
        materialsLink: 'https://static.turbosquid.com/Preview/2019/06/18__05_46_22/00.jpg4091F190-46D5-4DB5-A304-FF1EEA07899FZoom.jpg'
      },
      {
        title: 'Make task 4',
        color: 'amber',
        year: '02.12.1990',
        materialsLink: 'https://static.turbosquid.com/Preview/2019/06/18__05_46_22/00.jpg4091F190-46D5-4DB5-A304-FF1EEA07899FZoom.jpg'
      },
      {
        title: 'Make task 5',
        color: 'orange',
        year: '02.12.2000',
        materialsLink: 'https://static.turbosquid.com/Preview/2019/06/18__05_46_22/00.jpg4091F190-46D5-4DB5-A304-FF1EEA07899FZoom.jpg'
      }
    ]
  })
}
</script>
