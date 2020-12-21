<template>
  <b-table hover :items="items" :fields="fields"></b-table>
</template>

<script>
// console.log('this works?');

export default {
  props: {
    tableData: Array,
  },
  data() {
    return {
      fields: ["title", "publisher", "publicationDate", "isbn", "id"],
      items: this.tableData,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
