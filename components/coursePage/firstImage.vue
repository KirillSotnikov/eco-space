
<template>
  <v-img
    dark
    src="https://litreactor.com/sites/default/files/imagecache/header/images/column/headers/21741565422_0201bb9188_o.jpg"
    height="400"
  >
    <v-row
      align="center"
      justify="center"
      style="height: 100%;"
    >
      <v-col class="text-center" cols="12">
        <h1 v-if="title" class="display-1 font-weight-thin mb-4">{{title}}</h1>
        <h4 v-if="subtitle" class="subheading">{{subtitle}}</h4>
      </v-col>
    </v-row>
  </v-img>
</template>

<script>
export default {
  props: [
    'title',
    'subtitle'
  ]
}
</script>
