<template>
  <div class="container mt-4">
    <h2 class="mb-3">Tabla de Usuarios</h2>
    <table class="table table-striped table-bordered">
      <thead class="table-dark">
        <tr>
          <th>Nombre</th>
          <th>Apellido</th>
          <th>Correo</th>
          <th>Fecha de Nacimiento</th>
          <th>Edad</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(user, index) in users" :key="index">
          <td>{{ user.nombre }}</td>
          <td>{{ user.apellido }}</td>
          <td>{{ user.correo }}</td>
          <td>{{ user.fechaNacimiento }}</td>
          <td>{{ user.edad }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'TablaUsuarios',
  props: {
    users: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>
h2 {
  color: #0d6efd;
}
</style>
