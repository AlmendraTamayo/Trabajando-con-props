<template>
  <div>
    <h1 class="h1">{{ title }}</h1>
    <TodoTaskInput @nueva-tarea="agregarTarea" />
    <TodoListItems :tareas="tareas" @borrar-tarea="borrarTarea" />
  </div>
</template>

<script>
import TodoTaskInput from '@/components/TodoTaskInput.vue'
import TodoListItems from '@/components/TodoListItems.vue'
export default {
  name: 'Todo',
  components: {
    TodoTaskInput,
    TodoListItems,
  },
  props: {
    title: {
      type: String,
      required: true,
    },
  },
  data: () => ({
    nuevaTarea: '',
    tareas: [],
  }),
  methods: {
    agregarTarea(nuevaTarea) {
      this.tareas.push({ texto: nuevaTarea, $index: this.tareas.length })
    },
    borrarTarea(tareaABorrar) {
      this.tareas = this.tareas.filter((tarea) => tarea.$index !== tareaABorrar.$index)
    },
  },
}
</script>

<style>
.h1 {
  color: brown;
  text-align: center;
  text-decoration: underline;
}
</style>
