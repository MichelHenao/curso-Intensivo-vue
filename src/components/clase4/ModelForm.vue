<template>
    <div>
        <form>
        <input type="text" v-model="inputText">
        <input type="checkbox" v-model="agree"> acepto los terminos y condiciones
        <select name="" id="" v-model="country">
            <option value="spain">spain</option>
            <option value="UK">UK</option>
            <option value="France">France</option>
        </select>
    </form>

    <h3>{{ inputText }}</h3>
    </div>
    
</template>

<script setup>
import {ref} from 'vue'
    let inputText = ref('')
    let agree=ref(true)
    let country = ref("UK")
</script>

<style lang="sass" scoped>

</style>