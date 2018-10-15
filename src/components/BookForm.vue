
<template>
<form v-on:submit.prevent="bookSubmit(bookTitle,bookAuthor,bookPrice)" class="" action="#" method="post">
    <input type="text" name="title" value="" placeholder="Book Title" v-model="bookTitle">
    <input type="text" name="author" value="" placeholder="Book Author" v-model="bookAuthor">
    <input type="number" name="author" value="" placeholder="Book Price" v-model="bookPrice">
    <button type="submit" name="button">Add Book</button>
</form>
</template>

<script>
export default {
    name:'BookForm',
    props:['books'],
    data(){
        return{
           bookTitle:'',
           bookAuthor:'',
           bookPrice:'',
        }
    },
    methods:{
        bookSubmit(bookTitle,bookAuthor,bookPrice){
            if(bookTitle =="" && bookAuthor=="" && bookPrice==""){
                this.$swal('Title , Author and Price is Required','OK')
            }
            else if(bookTitle=="" && bookAuthor==""){
                  this.$swal('Title and  Author is Required','OK')
            }
            else if(bookPrice=="" && bookAuthor==""){
                  this.$swal('Author and Price is Required','OK')
            }
            else if(bookTitle=="" && bookPrice==""){
                  this.$swal('Title and price  is Required','OK')
            }
            else if(bookTitle==""){
                this.$swal('Title is Required','OK')
            }
            else if(bookAuthor==""){
                this.$swal('Author is Required','OK')
            }
            else if(bookPrice==""){
                this.$swal('Price is Required','OK')
            }
            else{
            this.$emit('addBook',bookTitle,bookAuthor,bookPrice)
            }
        }
    }
}
</script>

<style>
</style>

