<template>

<form v-on:submit.prevent="bookSubmit(bookTitle, bookAuthor, bookPrice)" method="post" action="#">
	<input type="text" v-model="bookTitle" name="title" value="" placeholder="Book Title">
	<input type="text" v-model="bookAuthor" name="author" value="" placeholder="Author">
  <input type="number" v-model="bookPrice" name="price" placeholder="Price">
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
    bookAuthor: '',
    bookPrice
    }
  },
  methods: {
    bookSubmit(bookTitle, bookAuthor, bookPrice) {
      if(bookTitle == '' || !bookTitle)
        this.$swal('Title is Required', 'OK')
      else if(bookAuthor == '' || !bookAuthor)
        this.$swal('Author is Required', 'OK')
      else if(!bookPrice)
        this.$swal('Price is Required', 'OK')
      else 
        this.$emit('addBook', bookTitle, bookAuthor, bookPrice)
     }
}
};

</script>

<style>



</style>
