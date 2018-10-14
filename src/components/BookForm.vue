<template>

<form v-on:submit.prevent="bookSubmit(bookTitle, bookAuthor)" method="post" action="#">
	<input type="text" v-model="bookTitle" name="title" value="" placeholder="Book Title">
	<input type="text" v-model="bookAuthor" name="author" value="" placeholder="Author">
	<button type="submit" name="button"> Add Book </button>
</form>

</template>

<script>

export default {
  name: 'BookForm',
  props: ['books'],
  data() {
    return {
    bookTitle: '',
    bookAuthor: ''
    }
  },
  methods: {
    bookSubmit(bookTitle, bookAuthor) {
      this.$emit('addBook', bookTitle, bookAuthor)
    }
  }
};

</script>

<style>



</style>
