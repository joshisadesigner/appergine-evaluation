<template>
  <b-table hover :items="items" :fields="fields"></b-table>
</template>

<script>
// console.log('this works?');

export default {
  mounted() {
    const formatDate = (date) => {
      const d = new Date(date);
      const YY = d.getFullYear();
      const MM = d.getMonth();
      const DD = d.getDay();

      return `${MM}/${DD}/${YY}`;
    };

    const booksInfo = (array) => {
      const ar = array;
      const result = ar.map((obj) => {
        obj.publicationDate = formatDate(obj.publicationDate);
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
