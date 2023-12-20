<template>
    <!-- ejemplo directiva v-if -->
    <!-- <h1 v-if="age < 18">Eres menor de edad </h1>
    <h1 v-else>Eres mayor de edad </h1>

     ejemplo directiva v-show -->
    <!--<h1 v-show="age < 18">Eres menor de edad </h1>
    <h1 v-show="age > 18">Eres mayor de edad </h1> -->

    <!-- directiva v-for -->
    <!-- <ul>
        <li v-for="country in countries" v-bind:key="country.code">{{ country.name }}</li>
    </ul> -->

    <!-- <p v-bind:class="{
        'danger' : hasError
    }">El mensaje se ha enviado satisfactoriamente</p> -->

    <!-- ejemplo bilding de estilos -->

    <div>
            <p v-bind:style="{
        backgroundColor : '#ccc', color : c
    }">El mensaje se ha enviado satisfactoriamente
    </p>

    <button v-on:click="handleClick()">cambiar color</button>
    </div>

</template>

<script setup>

import {ref} from 'vue';
// let hasError = true ;

// let countries = ref(
//     [{
//         code:'es',
//         name:'spain'
//     },
//     {
//         code:'fr',
//         name:'france'
//     },
//     {
//         code:'en',
//         name:'uk'
//     }
//         ]
// )
    // let age=10

    let c = ref('#fff')
    const handleClick= () => {c.value = '#ff0000'}
</script>

<style scoped>
/* .danger{
    color: red;
} */
</style>