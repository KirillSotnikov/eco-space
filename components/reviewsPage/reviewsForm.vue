<template>
  <v-form
    ref="form"
    style="max-width:800px;"
    class="mr-auto"
  >
    <h2 class="mb-4">Add your review</h2>
    <v-textarea
      outlined
      name="input-7-4"
      label="Your review"
      color="grey lighten-1"
      v-model="textarea"
    ></v-textarea>
    <v-btn
      tile
      outlined
      color="grey lighten-1"
      class="mr-4"
    >
      Send
    </v-btn>
  </v-form>
</template>

<script>
export default {
  data () {
    return {
      textarea: ''
    }
  }
}
</script>
