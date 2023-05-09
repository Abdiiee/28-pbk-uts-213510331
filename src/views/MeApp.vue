<script>
let id = 0

export default {
  data() {
    return {
      newTodo: '',
      hideCompleted: false,
      todos: [
      ]
    }
  },
  computed: {
    filteredTodos() {
      return this.hideCompleted
        ? this.todos.filter((t) => !t.done)
        : this.todos
    }
  },
  methods: {
    addTodo() {
      this.todos.push({ id: id++, text: this.newTodo, done: false })
      this.newTodo = ''
    },
    removeTodo(todo) {
      this.todos = this.todos.filter((t) => t !== todo)
    }
  }
}
</script>

<template>
  <h1>Kegiatan Ekstrakulikuler</h1>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo" type="search" placeholder="Isi kegiatan..">
    <button class="tes">Tambahkan Kegiatan</button>
  </form>
  <ul class="todo-list">
    <li v-for="todo in filteredTodos" :key="todo.id">
      <input type="checkbox" v-model="todo.done">
      <span :class="{ done: todo.done }">{{ todo.text }}</span>
      <button class="tes tes1" @click="removeTodo(todo)">&#10006;
      </button>
    </li>
  </ul>
  <button class="tes" @click="hideCompleted = !hideCompleted">
    {{ hideCompleted ? 'Tampilkan' : 'Sembunyikan' }}
  </button>
</template>

<style>

.tes {
  background-color: #155e75;
  border: none;
  color: white;
  padding: 9px 10px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 10px;
  cursor: pointer;
}

.tes1 {
  padding: 5px 10px;
}

input[type="search"] {
  width: 50%;
  padding: 10px;
  font-size: 16px;
  border: 2px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  margin-top: 10px;
}

.done {
  text-decoration: line-through;
}

.todo-list {
  list-style: none;
  margin: 0;
  padding: 0;
}

li {
  font-size: 25px;
}
</style>