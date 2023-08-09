<script setup>

</script>

<template>
    <form class="todo-box" >
      <input class="input" type="text">
      <button class="btn" >Add</button>
    </form>
</template>

<style scoped>

.todo-box{
  border: 4px solid #727781;
  width: 500px;
  height: 600px;
  border-radius: 20px ;
  display: flex;
  justify-content: center;
  align-items: flex-start;
  padding: 20px;
}

.input{
  padding: 10px;
  font-size: 15px ;
  color: black;
  width: 400px;
  height: 18px;
  margin-right: 10px;
  /* border: none; */
}
.btn{
  width: 50px;
  height: 40px; 
}

</style>
