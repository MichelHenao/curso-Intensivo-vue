
import { onMounted } from 'vue';
<template>
    <div>
        <h3>hola </h3>
    </div>
</template>

<script setup>
import { onMounted, onUpdated} from 'vue'

onMounted(() => {
    console.log("mounted")
})

onUpdated(() => {
    console.log("updated")
})
</script>


<!-- <script>
import { defineComponent } from 'vue'

export default defineComponent({
   name: "cycleOption",
   data(){

   },
   created(){
    console.log("created")
   },
   mounted(){
    console.log("mounted")
   },
   updated(){
    console.log("updated")
    },
    unmounted(){
    console.log("destroyed")
}
})
</script> -->
