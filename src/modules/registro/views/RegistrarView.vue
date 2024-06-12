<template>
    <div>
        <h2>Formulario de registro</h2>
        <Form :validation-schema="schema" @submit="onSubmit">
            <div class="form">
                <label for="nombre">Nombre:</label>
                <Field v-model="nombre" type="text" name="nombre" id="nombre" placeholder="Ingrese su nombre"></Field>
                <ErrorMessage name="nombre"></ErrorMessage>
            </div>
            <div class="form">
                <label for="correo">Email:</label>
                <Field v-model="email" type="email" name="email" id="correo" placeholder="Ingrese su email"></Field>
                <ErrorMessage name="email"></ErrorMessage>
            </div>
            <div class="form">
                <button type="submit">Registrar</button>
            </div>
        </Form>
        
    </div>
</template>

<script setup>
import { Form, Field, ErrorMessage } from 'vee-validate';
import { schema } from '../schemas/validationSchema';
import { useRegistrarStore } from '../stores/RegistrarStore'
import { ref } from 'vue';

const RegistrarStore = useRegistrarStore();
const nombre = ref('')
const email = ref('')

const onSubmit = () =>{
    RegistrarStore.guardarRegistro(nombre.value, email.value)
    console.log("Se ha enviado correctamente")
}
</script>

<style scoped>
.form{
    margin-bottom: 10px;
}
</style>