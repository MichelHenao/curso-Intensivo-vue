<template>
    <div class="estilos">
        <input type="text" v-model="message">
        <h3>{{ message }}</h3>
        <h3>{{ reverse }}</h3>
    </div>
</template>

<script> 
import { defineComponent, ref, computed} from 'vue'

    export default defineComponent({
        name: 'computedExample',
        setup(){
            let message = ref('')
            const reverse = computed(() => message.value.split('').reverse().join(''))
            return {message, reverse}
        }
    })
</script>


<!-- <script> opcion api
import { defineComponent } from 'vue'

    export default defineComponent({
        name: 'computedExample',
        data(){
            return {
                message : ''
            }
        },

        computed:{
            reverse(){
                return this.message.split('').reverse().join('')
            }
        }
    })
</script> -->

<style scoped>
.estilos{
    color: blue;
}
</style>