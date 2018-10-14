
<template>
  <div>
    <h1>{{title}}</h1>
    <ul>
      <book-item v-for="book in books" :book="book"></book-item>
    </ul>
    <book-form @addBook="appendBook" ></book-form>
  </div>
</template>

<script>
import BookItem from './BookItem';
import BookForm from './BookForm';

export default{
  name:'BookList',
  components:{
    BookItem,
    BookForm
  },
  data(){
    return{
      title:'All Books',
      books:[
          {title: 'Self-Reliance', author: 'Ralph Waldo Emerson',price:300},
          {title: 'American Gods', author: 'Neil Gaiman',price:760},
          {title: 'Amusing Ourselves to Death', author: 'Neil Postman',price:700},
      ]
    }
  },
  methods:{
    appendBook(bookTitle,bookAuthor,bookPrice){
      this.books.push({title:bookTitle,author:bookAuthor,price:bookPrice});
    }
  }
}
</script>

<style>
h1,h2{
  font-weight:normal;
}
ul{
 list-style-type:none;
 padding: 0;
}
</style>
