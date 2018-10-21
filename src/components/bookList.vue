<template>
  <div>
    <h1>{{title}}</h1>
    <ul>
      <book-item v-for='book in books' :book="book"></book-item>
    </ul>
  </div>
</template>

<script>
  import bookItem from './bookItem';
  export default {
    name: 'Booklist',
    components : {
      BookItem
    },
    data(){
      return {
        title :'All vedaa',
        books :[
          {title: "kannada", author:'kuvempu'},
          {title: "English", author: "David champel"},
          {title: "MAthematics", author: "aryabhatta"},
        ]
      }
    }
  }

</script>

<style>
  h1, h2 {
    font-weight: normal
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    display:block;
    margin:0 10px;
  }
</style>
