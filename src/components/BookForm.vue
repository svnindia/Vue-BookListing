<template>
  <form class="" action="#" method="post" v-on:submit.prevent="bookSubmit(bookTitle,bookAuthor,price)">
    <input type="text" name="title" value="" placeholder="Book Title" v-model="bookTitle">
    <input type="text" name="author" value="" placeholder="Book Author" v-model="bookAuthor">
    <input type="number" name="author" value=""  placeholder="Price" v-model="price">
    <button type="submit" :disabled='isDisabled' name="button">Add Book</button>
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
      price: ""
    };
  },
  methods: {
    bookSubmit(bookTitle, bookAuthor, price) {
      this.$emit("addBook", bookTitle, bookAuthor, price);
      this.bookTitle = "";
      this.bookAuthor = "";
      this.price = "";
    }
  },
  computed: {
    isDisabled: function() {
      if (
        (this.bookTitle.length &&
          this.bookAuthor.length &&
          this.price.length) == ""
      ) {
        return true;
      }
    }
  }
};
</script>

<style>
</style>
