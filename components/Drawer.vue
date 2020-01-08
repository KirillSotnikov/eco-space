
<template>
  <div>
    <template>
      <v-list-item v-if="isAuthorised" two-line>
        <v-list-item-avatar>
          <img src="https://randomuser.me/api/portraits/women/81.jpg">
        </v-list-item-avatar>
        <v-list-item-content>
          <v-list-item-title>{{userInfo.firstName}} {{userInfo.secondName}}</v-list-item-title>
          <v-list-item-subtitle>{{userInfo.status}}</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
      <v-list-item v-else two-line>
        <v-list-item-avatar>
          <v-icon dark>mdi-account-circle</v-icon>
        </v-list-item-avatar>
        <v-list-item-content>
          <v-list-item-title>Guest</v-list-item-title>
          <!-- <v-list-item-subtitle>Logged In</v-list-item-subtitle> -->
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
        <v-list-item v-for="item in userLinksComputed" :key="item.title" @click="goTo(item.href)">
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
        { title: 'Booking', icon: 'mdi-application-import', href: '/booking' },
        { title: 'Contact Us', icon: 'mdi-contact-mail-outline', href: '/contact-us' }

      ],
      userInfo: {
        avatar: 'https://randomuser.me/api/portraits/women/81.jpg',
        firstName: 'Jane',
        secondName: 'Smith',
        status: 'Pupil',
        id: 1
      }
    }
  },
  methods: {
    goTo (href) {
      this.$router.push(href)
    }
  },
  computed: {
    userLinksComputed () {
      const userLinks = [
        { title: 'My Account', icon: 'mdi-account', href: '/users/1' },
        { title: 'Calendar', icon: 'mdi-calendar', href: '/calendar' },
        { title: 'Marks', icon: 'mdi-bookmark-multiple-outline', href: '/marks' },
        { title: 'Home work', icon: 'mdi-briefcase-outline', href: '/home-work' },
        { title: 'Groups', icon: 'mdi-account-multiple', href: '/groups' }
      ]
      const index = userLinks.findIndex(e => e.href === '/marks')
      userLinks[index].href = `${userLinks[index].href}?userId=${this.userInfo.id}`
      return userLinks
    }
  }
}
</script>

<style lang="scss" scoped>
.login-link{
  font-size: 13px;
  opacity: .7;
}
</style>
