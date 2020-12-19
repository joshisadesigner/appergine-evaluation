<template>
  <b-table hover :items="items" :fields="fields"></b-table>
</template>

<script>
export default {
  created() {
    console.log(this.items)  //undefined;
  },
  props: {
    records: Array,
  },
  data() {
    return {
      fields: ["title", "publisher", "publicationDate", "isbn", "id"],
      items: this.records,
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
