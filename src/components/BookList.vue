<template>
  <div>
    <h1>
      {{title}}
    </h1>
    <ul>
      <book-item v-for="book in books" :book="book"></book-item>
    </ul>
    <hr>
    <book-form @addBook="appendBook"></book-form>
  </div>

</template>

<script>
  import BookItem from './BookItem.vue'
  import BookForm from './BookForm.vue'
  export default {
    name: 'BookList',
    components:{
        BookItem,
        BookForm
    },
    data() {
      return {
        title: 'All Books',
        books:[
          {title:'Let Us C',author:'yashwant Kanetkar'},
          {title:'Concept of Physics',author:'H C Verma'},
          {title:'Mathematics By RD Sharma',author:'R D Sharma'}
        ]
      };
    },
    methods:{
      appendBook(at,au){
        this.books.push({title:at,author:au});
      }
    }
  };
</script>

<style >
  h1,h2 {
    font-weight:normal;
  }

  ul{
    list-style-type:none;
    padding:0
  }

</style>
