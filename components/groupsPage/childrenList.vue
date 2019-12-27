<template>
  <v-row>
    <v-col cols="12" md="4" v-for="(child, key) in children" :key="key">
      <v-card
        outlined
      >
        <v-list-item three-line>
          <v-list-item-content>
            <div class="overline mb-4">{{group}}</div>
            <v-list-item-title class="headline mb-1">{{child.firstName}} {{child.secondName}}</v-list-item-title>
            <v-list-item-subtitle>{{child.shortDescription}}</v-list-item-subtitle>
          </v-list-item-content>

          <v-list-item-avatar
            tile
            size="80"
            color="grey"
          >
            <img
              src="https://cdn.vuetifyjs.com/images/john.jpg"
              alt="John"
            >
          </v-list-item-avatar>
        </v-list-item>

        <v-card-actions>
          <v-btn
            tile
            outlined
            color="grey lighten-1"
            class="mr-4"
            :to="`/users/${child.id}`"
          >
            Profile
          </v-btn>
          <v-btn
            tile
            outlined
            color="grey lighten-1"
            class="mr-4"
            :to="`/marks?userId=${child.id}`"
          >
            {{child.firstName}} marks
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  props: [
    'children',
    'group'
  ]
}
</script>
