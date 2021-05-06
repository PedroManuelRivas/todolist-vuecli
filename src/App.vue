<template>
  <div id="app">
    <h1>Usuarios Registrados</h1>
    <hr />
    Nuevo usuario: <input v-model="usuario" @keyup.enter="addUser" />
    <button @click="addUser">Agregar</button>
    <Lista @deleleteUsuario="deleteUser" :usuarios="usuarios" />
  </div>
</template>

<script>
import Lista from "@/components/Lista";
export default {
  name: "App",
  components: {
    Lista,
  },
  data() {
    return {
      usuario: "",
      usuarios: [],
    };
  },
  methods: {
    deleteUser(index) {
      this.usuarios.splice(index, 1);
    },
    addUser() {
      const { usuario } = this;
      if (!usuario) return alert("Ingrese un valor en el input");
      this.usuarios.push(usuario);
      this.usuario = "";
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
