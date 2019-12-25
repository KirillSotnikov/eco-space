
<template>
  <div>
    <h1 class="advantages-title">{{title}}</h1>
    <v-expansion-panels>
      <v-expansion-panel
        v-for="(item,i) in advantages"
        :key="i"
      >
        <v-expansion-panel-header>{{item.title}}</v-expansion-panel-header>
        <v-expansion-panel-content>
          {{item.description}}
        </v-expansion-panel-content>
      </v-expansion-panel>
    </v-expansion-panels>
  </div>
</template>

<script>
export default {
  props: [
    'title',
    'advantages'
  ]
}
</script>

<style lang="scss">
  .advantages-title{
    margin-top: 20px;
    margin-bottom: 20px;
  }
</style>
