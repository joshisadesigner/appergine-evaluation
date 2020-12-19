<template>
  <b-container id="app">
    <b-row>
      <b-col>
        <div class="table--continer">
          <Table v-bind:records="records" />
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import Table from './components/Table';
import recordsData from './mook/records.json'

export default {
  name: 'App',
  data() {
    return {
      records: recordsData,
    }
  },
  components: { Table },
}
</script>

<style>
</style>