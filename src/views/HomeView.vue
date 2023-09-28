<template>
  <form @submit.prevent="procesarFormulario">
    <input type="text" class="form-control my-2" placeholder="Ingrese Nombre" v-model.trim="tarea.nombre" />
    <div class="form-check form-check-inline">
      <input type="checkbox" class="form-check-input" id="check1" value="javascript" v-model="tarea.categorias" />
      <label for="check1" class="form-check-label">JavaScript</label>
    </div>
    <div class="form-check form-check-inline">
      <input type="checkbox" class="form-check-input" id="check2" value="typescript" v-model="tarea.categorias" />
      <label for="check2" class="form-check-label">TypeScript</label>
    </div>
    <div class="form-check form-check-inline">
      <input type="checkbox" class="form-check-input" id="check3" value="nodejs" v-model="tarea.categorias" />
      <label for="check3" class="form-check-label">NodeJS</label>
    </div>
    <div class="mt-2">
      <div class="form-check form-check-inline">
        <input class="form-check-input" type="radio" id="radio1" value="urgente" v-model="tarea.estado" />
        <label class="form-check-label" for="radio1">Urgente</label>
      </div>
      <div class="form-check form-check-inline">
        <input class="form-check-input" type="radio" id="radio1" value="relax" v-model="tarea.estado" />
        <label class="form-check-label" for="radio2">Relax</label>
      </div>
    </div>
    <div class="mt-2">
      <input class="form-control" type="number" v-model.number="tarea.numero" id="">
    </div>
    <button :disabled="bloquear" class="btn btn-dark mt-2 btn-block" type="submit">Procesar</button>
  </form>
  <p>{{ tarea }}</p>
</template>

<script>
export default {
  name: 'HomeView',
  components: {

  },
  data() {
    return {
      tarea: {
        nombre: '',
        numero: 0,
        categorias: [],
        estado: ''
      }
    }
  },
  methods: {
    procesarFormulario() {
      console.log(this.tarea)
      if (this.tarea.nombre.trim() === '') {
        console.log('Campo Vacío')
        return
      }
      console.log('No está Vacío')
      // Enviar los datos
      this.tarea = {
        nombre: '',
        numero: 0,
        categorias: [],
        estado: ''
      }
    }
  },
  computed: {
    bloquear() {
      return this.tarea.nombre.trim() === '' ? true : false
    }
  }
}
</script>
