<template>
  <div>
    <form @submit.prevent="">
      <fieldset>
        <legend>Formulario Ejemplo</legend>
        <InputComponent label="ingrese su usuario" v-model="username" tipo="text" cant_caracteres="4" width="300px"
          height="30px" />
        <InputComponent label="ingrese su email" v-model="email" tipo="email" cant_caracteres="4" width="300px"
          height="30px" />
        <InputComponent label="ingrese su password" v-model="password" tipo="password" cant_caracteres="6" width="300px"
          height="30px" />
        <InputComponent label="ingrese su fecha nacimiento" v-model="fecha_nac" tipo="date" cant_caracteres="6"
          width="300px" height="30px" />
      </fieldset>
    </form>
    <div class="datos">
      <h2> username <strong>{{ newUsuario.username }}</strong></h2>
      <h3>email <strong>{{ newUsuario.email }}</strong></h3>
      <h4>password <strong>{{ newUsuario.password }}</strong></h4>
    </div>
  </div>

</template>

<script setup lang="ts">
import { computed, ref } from 'vue';
import InputComponent from './components/InputComponent.vue';

const username = ref('');
const email = ref('');
const password = ref('');
const fecha_nac = ref('');

const newUsuario = computed(() => {
  return {
    username: username.value,
    email: email.value,
    password: password.value
  };
});

</script>

<style scoped>
div {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 10px;
}

fieldset,
.datos {
  margin: 0.5rem;
  border: 2px solid green;
  padding: 2rem 1rem;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  gap: 10px;
  background: linear-gradient(to right, #19222c, #1e1e1e);
}
</style>
