<template>
  <li>
    <div class="listItem">
      <div v-if="!tarea.modificable">{{ tarea.$index + 1 }} : {{ tarea.texto }}</div>

      <button class="boton" @click="borrar(tarea)">eliminar</button>
    </div>
  </li>
</template>

<script>
export default {
  name: 'TodoListItem',
  props: {
    tarea: {
      type: Object,
      required: true,
    },
  },
  methods: {
    borrar(tarea) {
      this.$emit('borrar-tarea', tarea)
    },
  },
}
</script>

<style>
.listItem {
  display: flex;
  margin-top: 10px;
}
</style>
