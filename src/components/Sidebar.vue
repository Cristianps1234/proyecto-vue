<template>
    <div class="sidebar">
        <h2>Bienvenido</h2>
        <h3>Nombre: {{ nombre }}</h3>
        <h3>Email: {{ email }}</h3>
        <ul>
            <li><router-link to="/contador">Contador</router-link></li>
            <li><router-link to="/Lista-de-tareas">Lista de Tareas</router-link></li>
            <li><router-link to="/registrar">Registrar</router-link></li>
        </ul>
        
        
    </div>
</template>

<script setup>
import { useRegistrarStore } from '@/modules/registro/stores/RegistrarStore';
import { ref, watch } from 'vue';
const RegistrarStore = useRegistrarStore()
const nombre = ref(RegistrarStore.nombre.value)
const email = ref(RegistrarStore.email.value)
watch(()=> RegistrarStore.nombre, (newValue) =>{
    nombre.value = newValue
})
watch(()=> RegistrarStore.email, (newValue) =>{
    email.value = newValue
})
</script>

<style>
.sidebar{
    width: 200px;
    background-color: #f0f0f0;
    padding: 20px;
}
</style>