<template>
  <div class="container mt-4 border p-3 rounded bg-light">
    <h2>Registro de Usuario</h2>
    <form @submit.prevent="registrarUsuario">
      <div class="mb-3">
        <label for="nombre" class="form-label">Nombre</label>
        <input type="text" id="nombre" class="form-control" v-model="nombre" />
      </div>
      <div class="mb-3">
        <label for="apellido" class="form-label">Apellido</label>
        <input type="text" id="apellido" class="form-control" v-model="apellido" />
      </div>
      <div class="mb-3">
        <label for="correo" class="form-label">Correo electrónico</label>
        <input type="email" id="correo" class="form-control" v-model="correo" />
      </div>
      <div class="mb-3">
        <label for="fechaNacimiento" class="form-label">Fecha de Nacimiento</label>
        <input type="text" id="fechaNacimiento" class="form-control" v-model="fechaNacimiento" placeholder="MM/DD/YYYY" />
      </div>
      <div class="mb-3">
        <label for="edad" class="form-label">Edad</label>
        <input type="number" id="edad" class="form-control" v-model.number="edad" />
      </div>
      <button type="submit" class="btn btn-primary me-2">Registrar</button>
      <button type="button" class="btn btn-secondary" @click="limpiarFormulario">Limpiar</button>
    </form>

    <div v-if="mostrarResumen" class="mt-3 p-3 border rounded bg-white">
      <h4>Resumen del Usuario</h4>
      <p><strong>Nombre:</strong> {{ nombre }}</p>
      <p><strong>Apellido:</strong> {{ apellido }}</p>
      <p><strong>Correo:</strong> {{ correo }}</p>
      <p><strong>Fecha de Nacimiento:</strong> {{ fechaNacimiento }}</p>
      <p><strong>Edad:</strong> {{ edad }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'RegistroUsuario',
  data() {
    return {
      nombre: '',
      apellido: '',
      correo: '',
      fechaNacimiento: '',
      edad: ''
    }
  },
  computed: {
    mostrarResumen() {
      return this.nombre && this.apellido && this.correo && this.fechaNacimiento && this.edad
    }
  },
  methods: {
    registrarUsuario() {
      alert('Usuario registrado correctamente!')
      this.$emit('nuevo-usuario', {
        nombre: this.nombre,
        apellido: this.apellido,
        correo: this.correo,
        fechaNacimiento: this.fechaNacimiento,
        edad: this.edad
      })
      this.limpiarFormulario()
    },
    limpiarFormulario() {
      this.nombre = ''
      this.apellido = ''
      this.correo = ''
      this.fechaNacimiento = ''
      this.edad = ''
    }
  }
}
</script>

<style scoped>
h2 {
  color: #0d6efd;
}
</style>
