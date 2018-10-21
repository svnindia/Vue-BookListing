<template>
<div>
  <h1>{{title}}</h1>
   <ul>
      <li v-for='book in books'>{{book.title}}:{{book.author}}</li>
   </ul>
</div>


</template>

<script>
export default {
  name: 'Booklist',
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
li{
  display:block;
  margin:0 10px;
}
</style>
