<template>
  <div>
    <!-- Ввод задачи -->
    <input type="text" v-model="newTodo" placeholder="Введите задачу" />
    <button @click="addTodo">Добавить</button>

    <!-- Список задач -->
    <ul>
      <li v-for="(todo, index) in todos" :key="index">
        {{ todo }}
        <button @click="deleteTodo(index)">Удалить</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "ToDoList",
  data() {
    return {
      newTodo: "",
      todos: [],
    };
  },
  mounted() {
    // При загрузке компонента, попытаемся получить сохраненные задачи из Local Storage
    const savedTodos = localStorage.getItem("todos");
    if (savedTodos) {
      this.todos = JSON.parse(savedTodos);
    }
  },
  methods: {
    addTodo() {
      this.todos.push(this.newTodo);
      this.newTodo = "";
      this.saveTodos(); // Сохраняем задачи в Local Storage после добавления новой задачи
    },
    deleteTodo(index) {
      this.todos.splice(index, 1);
      this.saveTodos(); // Сохраняем задачи в Local Storage после удаления задачи
    },
    saveTodos() {
      // Сохраняем задачи в Local Storage в виде строки JSON
      localStorage.setItem("todos", JSON.stringify(this.todos));
    },
  },
};
</script>

<style scoped>
/* Стили компонента */
</style>
