<template>
  <div class="lista-personajes mt-4">
    <h2>Lista de Personajes Ficticios</h2>
    <ul>
      <li v-for="personaje in data.personajes" :key="personaje.id" class="personaje">
        <strong>{{ personaje.nombre }}</strong>: {{ personaje.descripcion }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'ListaPersonajes',
  data() {
    return {
      data: {
        personajes: [
          { id: '1', nombre: 'pikachu', descripcion: 'lorem ipsum uhiuhiuhihoi' },
          { id: '2', nombre: 'kakuna', descripcion: 'lorem ipsum uhiuhiuhihoi' },
          { id: '3', nombre: 'beedrill', descripcion: 'lorem ipsum uhiuhiuhihoi' },
          { id: '4', nombre: 'metapod', descripcion: 'lorem ipsum uhiuhiuhihoi' },
          { id: '5', nombre: 'rattata', descripcion: 'lorem ipsum uhiuhiuhihoi' }
        ]
      }
    }
  }
}
</script>

<style scoped>
.lista-personajes {
  padding: 10px;
  border-top: 2px solid #0d6efd;
}

.personaje {
  margin: 6px 0;
}
</style>
