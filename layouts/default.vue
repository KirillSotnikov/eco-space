
<template>
  <!-- App.vue -->

  <v-app>
    <v-navigation-drawer v-model="isDrawer" app>
      <!-- -->
      <app-drawer />
    </v-navigation-drawer>

    <v-app-bar app>
      <!-- -->
       <v-app-bar-nav-icon @click="toggleDrawer"></v-app-bar-nav-icon>

      <v-toolbar-title >
        <nuxt-link class="d-flex align-center header-link" to="/">
          <v-icon style="margin-right: 5px;">mdi-compass</v-icon>
          Eco Space
        </nuxt-link>
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-menu
        left
        bottom
      >
        <template v-slot:activator="{ on }">
          <v-btn icon v-on="on">
            <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>
        </template>

        <v-list>
          <v-list-item
            v-for="n in 5"
            :key="n"
            @click="() => {}"
          >
            <v-list-item-title>Option {{ n }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>

    <!-- Sizes your content based upon application components -->
    <v-content>

      <!-- Provides the application the proper gutter -->
      <v-container fluid>

        <!-- If using vue-router -->
        <nuxt/>
      </v-container>
    </v-content>

    <app-footer />
  </v-app>
</template>

<script>
import appDrawer from '@/components/Drawer.vue'
import appFooter from '@/components/Footer.vue'
export default {
  components: {
    'app-drawer': appDrawer,
    'app-footer': appFooter
  },
  data () {
    return {
      isDrawer: false
    }
  },
  methods: {
    toggleDrawer () {
      this.isDrawer = !this.isDrawer
    }
  }
}
</script>

<style lang="scss" scoped>
.header-link{
  text-decoration: none;
  color: #fff;
}
</style>
