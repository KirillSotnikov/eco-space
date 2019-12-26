
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
      <v-list-item v-for="item in links" :key="item.title" @click="goTo(item.href)">
        <v-list-item-icon>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-item-icon>
        <v-list-item-content>
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
      <div v-if="isAuthorised">
        <v-divider/>
        <v-list-item v-for="item in userLinks" :key="item.title" @click="goTo(item.href)">
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </div>
    </v-list>
  </div>
</template>

<script>
export default {
  data () {
    return {
      isAuthorised: true,
      links: [
        { title: 'Home', icon: 'mdi-home-city', href: '/' },
        { title: 'About Us', icon: 'mdi-auto-fix', href: '/about' },
        { title: 'Courses', icon: 'mdi-book-open-page-variant', href: '/courses' },
        { title: 'News', icon: 'mdi-newspaper', href: '/news' },
        { title: 'Reviews', icon: 'mdi-message-draw', href: '/reviews' },
        { title: 'Contact Us', icon: 'mdi-contact-mail-outline', href: '/contact-us' }

      ],
      userLinks: [
        { title: 'My Account', icon: 'mdi-account', href: '/account' },
        { title: 'Calendar', icon: 'mdi-calendar', href: '/calendar' },
        { title: 'Marks', icon: 'mdi-bookmark-multiple-outline', href: '/marks' },
        { title: 'Home work', icon: 'mdi-briefcase-outline', href: '/home-work' }
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
