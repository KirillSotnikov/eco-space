<template>
  <v-container fluid>
    <h1 class="groups-title">Groups</h1>
    <app-groups-table />
  </v-container>
</template>

<script>
import groupsTable from '@/components/Tables/groupTable.vue'
export default {
  components: {
    'app-groups-table': groupsTable
  }
}
</script>

<style lang="scss" scoped>
.groups-title{
  margin-top: 20px;
  margin-bottom: 20px;
}
</style>
