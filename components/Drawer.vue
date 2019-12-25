
<template>
  <div>
    <template>
      <v-list-item two-line>
        <v-list-item-avatar>
          <img src="https://randomuser.me/api/portraits/women/81.jpg">
        </v-list-item-avatar>
        <v-list-item-content>
          <v-list-item-title>Jane Smith</v-list-item-title>
          <v-list-item-subtitle>Logged In</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
    </template>
    <v-divider></v-divider>
    <v-list dense>
      <v-list-item v-for="item in items" :key="item.title" @click="goTo(item.href)">
        <v-list-item-icon>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-item-icon>
        <v-list-item-content>
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </div>
</template>

<script>
export default {
  data () {
    return {
      items: [
        { title: 'Home', icon: 'mdi-home-city', href: '/' },
        { title: 'My Account', icon: 'mdi-account', href: '/account' },
        { title: 'Calendar', icon: 'mdi-calendar', href: '/calendar' },
        { title: 'Courses', icon: 'mdi-book-open-page-variant', href: '/courses' }
      ]
    }
  },
  methods: {
    goTo (href) {
      this.$router.push(href)
    }
  }
}
</script>
