<template>
  <b-table hover :items="items" :fields="fields"></b-table>
</template>

<script>
// console.log('this works?');

export default {
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
  props: {
    records: Array,
  },
  data() {
    return {
      fields: ["title", "publisher", "publicationDate", "isbn", "id"],
      items: this.records,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
