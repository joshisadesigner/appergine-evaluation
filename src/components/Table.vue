<template>
  <b-table
    hover
    responsive
    sticky-header
    no-border-collapse
    :items="items"
    :fields="fields"
  ></b-table>
</template>

<script>
// console.log('this works?');

export default {
  props: {
    tableData: Array,
  },
  data() {
    return {
      fields: [
        {
          key: "title",
          stickyColumn: true,
          isRowHeader: true,
        },
        "publisher",
        "publicationDate",
        "isbn",
        "id",
      ],
      items: this.tableData,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
