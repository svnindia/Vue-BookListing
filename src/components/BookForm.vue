<template>
  <form action="#" method="post" v-on:submit.prevent="bookSubmit(bookTitle,bookAuthor)">
    <input v-model="bookTitle" type="text" placeholder="Title">
    <input v-model="bookAuthor" type="text" placeholder="Author">
    <button type="submit">Add Book</button>
  </form>

</template>
<script>
  export default{
    name:"BookForm",
    props:["books"],
    data(){
      return {
        bookTitle:'',
        bookAuthor:''
      }
    },
    methods:{
      bookSubmit(bookTitle,bookAuthor){
        this.$emit('addBook',bookTitle,bookAuthor);

      }
    }
  }
</script>
<style></style>
