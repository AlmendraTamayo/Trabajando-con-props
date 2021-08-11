<template>
  <div class="centrar">
    <label class="tarea">Tarea </label>
    <input type="text" placeholder="Ingresa nueva tarea" v-model="nuevaTarea" />
    <button class="boton" @click="handleClick">Añade</button>
  </div>
</template>

<script>
export default {
  name: 'TodoTaskInput',
  data: () => ({
    nuevaTarea: '',
  }),
  methods: {
    handleClick() {
      this.$emit('nueva-tarea', this.nuevaTarea)
      this.nuevaTarea = ''
    },
  },
}
</script>

<style>
.centrar {
  display: flex;
  justify-content: center;
}
.tarea {
  font-weight: bold;
  margin-right: 5px;
}
.boton {
  margin-left: 5px;
}
</style>
