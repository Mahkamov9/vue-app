
<template class="box">
  <div class="todo-list">
    <h1 class="text">To do app</h1>
    <div>
      <input class="input" v-model="newTodo" @keyup.enter="addTodo" placeholder="Add a new task" />
      <button class="btn" @click="addTodo">Add</button>
    </div>
    <ul class="task-list">
      <li class="task-list-item" v-for="(todo, i) in todos" :key="i">
        <div class="label">
          <input class="checkbox" type="checkbox">
          <span>{{ todo.text }}</span>
        </div>
        <button class="remove-btn" @click="removeTodo(i)">Remove</button>
        <button class="edit-btn">Edit</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todos: [],
      newTodo: '',
    };
  },
  methods: {
    addTodo() {
      if (this.newTodo.trim() === '') return;
      this.todos.push({ text: this.newTodo });
      this.newTodo = '';
    },
    removeTodo(i) {
      this.todos.splice(i, 1);
      this.todos.splice(i, 1);

    },
  },
};
</script>

<style scoped>

.todo-list {
  background-color: rgba(74, 32, 114, 0.737);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  border-radius: 15px;
  border: 1px solid black;
  width: 400px;
  height: 500px;
  color: #fff;
}

.text {
  font-size: 40px;
  font-weight: bold;
}

.input {
  width: 300px;
  height: 25px;
  margin-right: 10px;
  border-radius: 10px;
  outline: none;
  /* border: none; */
  padding-left: 25px;
  font-size: 15px;
}

.btn{
  border-radius: 10px;
  outline: none;
  border: none;
  width: 40px;
  height: 28px;
  color: #fff;
  background-color: rgba(0, 0, 0, 0.582);
}


ul {
  overflow-y: hidden;
  list-style-type: none;
  padding: 0;

}

li {
  /* position: absolute; */
  font-size: 20px;
  padding-top: 5px;
  width: 360px;
  height: 30px;
  margin-bottom: 5px;
  background-color: rgba(0, 0, 0, 0.119);
  border-radius: 10px;
  padding-left: 25px;

}

.task-list-item input:checked ~ span {
  text-decoration: line-through;
}

.remove-btn{
  display: flex;
  position: relative;
  margin-left: auto;
  margin-right: 8px;
  border: none;
  border-radius: 10px;
  background-color: #fff;
  padding: 5px;
  transform: translate(0% , -85%);

}

.edit-btn{
  display: flex;
  position: relative;
  margin-left: auto;
  margin-right: 8px;
  border: none;
  border-radius: 10px;
  background-color: #fff;
  padding: 5px;
  transform: translate(-200% , -185%);

}
</style>
