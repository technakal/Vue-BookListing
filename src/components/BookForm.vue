<template>
  <form class action="#" method="post" @submit.prevent="bookSubmit(bookTitle, bookAuthor)">
    <input type="text" name="title" value v-model="bookTitle" placeholder="Book title" />
    <input type="text" name="author" value v-model="bookAuthor" placeholder="Book athor" />
    <button type="submit" name="button">Add Book</button>
  </form>
</template>
<script>
export default {
  name: "BookForm",
  props: ["books"],
  data() {
    return {
      bookTitle: "",
      bookAuthor: "",
    };
  },
  methods: {
    bookSubmit(bookTitle, bookAuthor) {
      this.$emit("addBook", bookTitle, bookAuthor);
    },
  },
};
</script>
<style></style>