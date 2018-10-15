
<template>
<ul>
    <li>{{book.title}}:{{book.author}}:{{book.price}}</li>
</ul>
</template>

<script>
export default {
    name:'BookItem',
    props:['book']
}
</script>

<style>
li{
  margin:0 10px;
  display:block;
}
</style>


