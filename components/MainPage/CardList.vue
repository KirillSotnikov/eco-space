
<template>
  <div>
    <h1 v-if="title" class="services-title">{{title}}</h1>
    <v-row>
      <v-col
        v-for="(subject, key) in subjects"
        :key="key"
        cols="12"
        sm="4"
      >
        <v-card
        class="service-card"
        >
          <v-img
            class="white--text align-end"
            height="200px"
            :src="subject.url"
          >
            <v-card-title>
              {{subject.title}}
            </v-card-title>
          </v-img>

          <v-card-subtitle class="pb-0">
            <b>Courses start: </b>{{subject.date}}
          </v-card-subtitle>

          <v-card-text class="text--primary">
            <div>
              <b>Teacher: </b>{{subject.teacher}}
            </div>

            <div>
              {{subject.shortDescription}}
            </div>
          </v-card-text>

          <v-card-actions>
            <v-btn
              color="orange"
              text
              to="courses/11"
            >
              Read more
            </v-btn>

            <v-btn
              color="orange"
              text
              to="/booking"
            >
              Book now
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  props: [
    'subjects',
    'title'
  ],
  filters: {
    date (value, withTime) {
      const options = {
        year: 'numeric',
        month: 'long',
        day: '2-digit'
      }

      return new Intl.DateTimeFormat('ru-RU', options).format(new Date(+value))
    }
  }
}
</script>

<style lang="scss">
  .services-title{
    margin-top: 20px;
    margin-bottom: 20px;
  }
</style>
