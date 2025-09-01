<template>
  <div class="container mt-4">
    <h1 class="mb-4">Gestión de Usuarios</h1>
    
    <TablaUsuarios :users="users" />
    <RegistroUsuario @nuevo-usuario="agregarUsuario" />

    <!-- Lista de personajes -->
    <ListaPersonajes />
  </div>
</template>

<script>
import TablaUsuarios from './TablaUsuarios.vue'
import RegistroUsuario from './RegistroUsuario.vue'
import ListaPersonajes from './components/ListaPersonajes.vue'

export default {
  name: 'App',
  components: {
    TablaUsuarios,
    RegistroUsuario,
    ListaPersonajes
  },
  data() {
    return {
      users: [
        { nombre: "Juan", apellido: "Pérez", correo: "juan.perez@email.com", fechaNacimiento: "1990-05-12", edad: 33 },
        { nombre: "María", apellido: "González", correo: "maria.gonzalez@email.com", fechaNacimiento: "1985-11-23", edad: 37 },
        { nombre: "Carlos", apellido: "Ramírez", correo: "carlos.ramirez@email.com", fechaNacimiento: "2000-02-07", edad: 23 }
      ]
    }
  },
  methods: {
    agregarUsuario(usuario) {
      this.users.push(usuario)
    }
  }
}
</script>

<style scoped>
h1 {
  color: #0d6efd;
}
</style>

