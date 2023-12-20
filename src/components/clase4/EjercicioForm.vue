<template>
    <div>
        <section>
            <h3>Añadir profesores</h3>
            <div>
                <label for="">Nombre:</label> <input type="text" v-model="teacher.teacherName">
                <label for="">Apellidos:</label> <input type="text" v-model="teacher.surname">
                <label for="">DNI / NIF:</label> <input type="text" v-model="teacher.dni">
                <label for="">Materias:</label> <input type="text" v-model="materias"><button @click="handleMaterias">agregar</button>
                <div>
                    <ul>
                        <li v-for="(elm, index) in teacher.materia" :key="index">{{ elm }}</li>
                    </ul>
                </div>
                <input type="checkbox" v-model="teacher.check"> Documentacion entregada 
                <button @click="handleAddTeacher">Agregar</button>
            </div>
        </section>

        <section>
            <h3>Listado de profesores</h3>
            <table>
                <tr>
                    <th>Nombre</th>
                <th>apellidos</th>
                <th>DNI/ NIF</th>
                <th>Materias</th>
                <th>documentacion entregada</th>
                </tr>

                <tr v-for="elm in teachers" :key="elm.dni">
                    <th>{{ elm.teacherName }}</th>
                    <th>{{ elm.surname }}</th>
                    <th>{{ elm.dni }}</th>
                    <th>
                        <ul>
                            <li v-for="(item, index) in elm.materia" :key="index">{{ item }}</li>
                        </ul>
                    </th>
                    <th v-if="elm.check">Entregada</th>
                    <th v-else>No entregada</th>
                </tr>    
                
            </table>
        </section>
    </div>
    
</template>

<script setup>
import {ref} from 'vue'

    let teacher = ref({
        teacherName: '',
        surname: '',
        dni: '',
        materia: [],
        check: false,
    })

    let teachers = ref([])

    let materias = ref('')

    const handleMaterias = () => {
        teacher.value.materia.push(materias.value)
        materias.value = ""
    }

    const handleAddTeacher = () => {
        teachers.value.push({
            teacherName:teacher.value.teacherName,
            surname : teacher.value.surname,
            dni: teacher.value.dni,
            materia: teacher.value.materia,
            check: teacher.value.check,
        })
        teacher.value.teacherName= ""
        teacher.value.surname= ""
        teacher.value.dni= ""
        teacher.value.materia= []
        teacher.value.check= false
    }
</script>

<style scoped>

</style>