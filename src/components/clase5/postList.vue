<template>
    <div class="container">
        <post-detail v-for="elm in info" :key="elm.title" :title="elm.title" :content="elm.content" @soyHi="showAlert"></post-detail>
    </div>
</template>

<script setup>
import postDetail from "./postDetail.vue";

    let info = [
        {title:"este es el post 1", content: "texto de ejemplo 1"},
        {title:"este es el post 2", content: "texto de ejemplo 2"},
        {title:"este es el post 3", content: "texto de ejemplo 3"},
        {title:"este es el post 4", content: "texto de ejemplo 4"},
        {title:"este es el post 5", content: "texto de ejemplo 5"}
    ]

    function showAlert(msg){
        alert(msg)
    }
</script>

<style scoped>
.container{
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    flex-direction: row;
}

</style>