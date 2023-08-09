<!-- <template>
  <h1 class="text">TO DO APP</h1>
  <div class="todo-box" id="todolist">

    <form class="form-box">
      <input class="input"
      type="text"
      @input="name $event.target.value" 
      />
      <button class="btn" >Add</button>
    </form>

    <ul class="task-list">
      <li class="task-list-item" v-for="task in todoArr">
        <label class="task-list-item-label">
          <input type="checkbox">
          <span>{{ task.title }}</span>
        </label>
        <span class="delete-btn" title="delete-task" @click="deltem(task)">{{ task.del }}</span>
      </li>
    </ul>

  </div>
</template>



<script>
export default {
  data() {
    return {
      todoArr: [
        { id: 1, title: "Salom" },
        { id: 2, title: "Hello" },
      ]
    }
  },
  methods: {
    changeHandleName(e){
      console.log(e.target.value);
    },
  },
}

</script>


<style scoped>
.text {
  text-align: center;
  color: aliceblue;
}

.todo-box {
  border: 4px solid #727781;
  width: 500px;
  min-width: 340px;
  min-height: 500px;
  border-radius: 20px;
  display: flex;
  flex-direction: column;
  padding: 20px;
}

.input {
  padding: 10px;
  font-size: 15px;
  color: black;
  width: 400px;
  height: 18px;
  margin-right: 10px;
  /* border: none; */
}

.btn {
  width: 50px;
  height: 40px;
}

.task-list-item {
  background-color: rgba(255, 255, 255, 0.3);
  display: flex;
  align-items: center;
  padding: 8px;
  border-radius: 5px;
  margin-top: 15px;
}

.task-list-item input:checked+span {
  text-decoration: line-through;
}

.task-list-item-label {
  display: flex;
  align-items: flex-start;
  position: relative;
  cursor: pointer;
  transition: 0.2s;
}

.delete-btn {
  margin-left: auto;
  margin-right: 5px;
  display: block;

}
</style> -->





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
    },
  },
};
</script>

<style scoped>

.todo-list {
  background-color: rgba(118, 49, 183, 0.737);
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



