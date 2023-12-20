<template>
    <div class="post">
        <h3>{{ props.title }}</h3>
        <p>{{ props.content }}</p>
        <input type="text" v-model="mesage">
        <button @click="handleClick">Hola</button>
    </div>
</template>

<script>
import { defineComponent } from 'vue';
import {ref} from 'vue';

export default defineComponent({
    name: 'postDetail',
    props:{
        title : {
            type: String,
            required: true
        },
        content: {
            type: String,
            required: false,
            default: "este post no tiene contenido"
        }
    },

    emits: ["soyHi"],

    setup(props, {emit}){

        const handleClick=() => {
            emit("soyHi",mesage.value)
        }

        let mesage= ref("")
        return {props,mesage, handleClick}
    }
})
</script>

<style scoped>
.post{
    width: 300px;
    border-radius: 10px;
    height: 200px;
    background-color: antiquewhite;
    margin: 10px;
    padding: 10px;
}
</style>