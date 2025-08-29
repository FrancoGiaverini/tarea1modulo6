<template>
  <div class="container mt-4">
    <h2 class="mb-3">Tabla de Usuarios</h2>
    <table class="table table-striped table-bordered">
      <thead class="table-dark">
        <tr>
          <th>Nombre</th>
          <th>Apellido</th>
          <th>Fecha de Nacimiento</th>
          <th>Edad</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(user, index) in users" :key="index">
          <td>{{ user.nombre }}</td>
          <td>{{ user.apellido }}</td>
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
  data() {
    return {
      users: [
        { nombre: "Juan", apellido: "Pérez", fechaNacimiento: "1990-05-12", edad: 33 },
        { nombre: "María", apellido: "González", fechaNacimiento: "1985-11-23", edad: 37 },
        { nombre: "Carlos", apellido: "Ramírez", fechaNacimiento: "2000-02-07", edad: 23 },
        { nombre: "Ana", apellido: "Torres", fechaNacimiento: "1995-08-15", edad: 28 },
        { nombre: "Luis", apellido: "Martínez", fechaNacimiento: "1988-03-30", edad: 35 },
        { nombre: "Sofía", apellido: "López", fechaNacimiento: "2002-12-01", edad: 20 }
      ]
    }
  }
} 
</script>
