<template>
  <div>
    <ol>
      <li v-for="(usuario, i) in usuarios" :key="i">
        {{ usuario }} <button @click="deleteUser(i)">Eliminar</button>
      </li>
    </ol>
  </div>
</template>

<script>
export default {
  props: ["usuarios"],
  methods: {
    deleteUser(index) {
      this.$emit("deleleteUsuario", index);
    },
  },
};
</script>