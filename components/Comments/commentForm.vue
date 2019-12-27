<template>
  <v-container style="max-width:800px;">
    <v-card class="d-flex align-start pa-4">
      <v-text-field @keyup.enter="addComment" v-model="commentText" label="Add comment"></v-text-field>
      <v-btn
        class=""
        fab
        dark
        color="grey darken-1"
        @click="addComment"
      >
        <v-icon dark>mdi-send</v-icon>
      </v-btn>
    </v-card>
    <v-list three-line>
      <template v-for="(comment, index) in comments">
        <v-subheader
          v-if="comment.header"
          :key="comment.header"
          v-text="comment.header"
        ></v-subheader>

        <v-divider
          v-else-if="comment.divider"
          :key="index"
          :inset="comment.inset"
        ></v-divider>

        <v-list-item
          v-else
          :key="comment.subtitle"
        >
          <v-list-item-avatar>
            <v-img :src="comment.avatar"></v-img>
          </v-list-item-avatar>

          <v-list-item-content>
            <v-list-item-subtitle v-html="comment.date"></v-list-item-subtitle>
            <v-list-item-title class="pre-wrap" v-html="comment.subtitle"></v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </template>
    </v-list>
  </v-container>
</template>

<script>
const userObject = {
  avatar: 'https://cdn.vuetifyjs.com/images/lists/5.jpg',
  date: '02.02.2020',
  subtitle: ''
}
export default {
  data: () => ({
    commentText: '',
    comments: [
      {
        avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg',
        date: '02.02.2020',
        subtitle: "I'll be in your neighborhood doing errands this weekend. Do you want to hang out? I'll be in your neighborhood doing errands this weekend. Do you want to hang out? I'll be in your neighborhood doing errands this weekend. Do you want to hang out?"
      },
      {
        avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
        date: '02.02.2020',
        subtitle: "Wish I could come, but I'm out of town this weekend. Wish I could come, but I'm out of town this weekend."
      },
      {
        avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg',
        date: '02.02.2020',
        subtitle: 'Do you have Paris recommendations? Have you ever been? Do you have Paris recommendations? Have you ever been?'
      },
      {
        avatar: 'https://cdn.vuetifyjs.com/images/lists/4.jpg',
        date: '02.02.2020',
        subtitle: 'Have any ideas about what we should get Heidi for her birthday? Have any ideas about what we should get Heidi for her birthday?'
      },
      {
        avatar: 'https://cdn.vuetifyjs.com/images/lists/5.jpg',
        date: '02.02.2020',
        subtitle: 'We should eat this: Grate, Squash, Corn, and tomatillo Tacos. We should eat this: Grate, Squash, Corn, and tomatillo Tacos.'
      }
    ]
  }),
  methods: {
    addComment () {
      userObject.subtitle = this.commentText
      this.comments.unshift(userObject)
      this.commentText = ''
    }
  }
}
</script>

<style lang="scss" scoped>
.pre-wrap{
  white-space: pre-wrap;
}
</style>
