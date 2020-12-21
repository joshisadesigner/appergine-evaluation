<template>
  <b-container id="app">
    <b-row>
      <b-col>
        <div class="a-table">
          <Table v-bind:records="records" />
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import Table from "./components/Table";
import recordsData from "./mook/records.json";

export default {
  name: "App",
  components: { Table },
  data() {
    return {
      records: recordsData,
    };
  },
  mounted() {
    const booksInfo = (array) => {
      const ar = array;
      const result = ar.map((obj) => {
        obj.publicationDate = new Date(obj.publicationDate).toDateString();
        return obj;
      });
      return result;
    };

    booksInfo(this.records);
  },
};
</script>

<style></style>
