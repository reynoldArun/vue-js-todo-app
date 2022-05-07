<template>
  <div class="container">
    <img alt="Vue logo" src="./assets/logo.png" class="vue-logo">
    <h1>To Do App</h1>
    <div class="content">
      <input type="text" v-model="inputState">
      <button @click="AddtoList">Add</button>
    </div>
  </div>
  <Todo-list v-for="(list, index) in todoList" :key="index" :todo="list" @delete-item="deleteitem(index)"/>
</template>

<script>

import TodoList from './components/TodoList.vue'

export default {
  components: {
    TodoList
  },
  data() {
    return {
      inputState : '',
      todoList: []
    }
  },
  methods: {
    AddtoList() {
      if(this.inputState) {
        this.todoList.push(this.inputState)
        this.inputState = ''
      } else {
        alert('Input Cannot be Empty!!!')
      }
    },
    deleteitem(n) {
      this.todoList.shift(n, 1)
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Macondo&display=swap');

    *, *::before, *::after {
        padding: 0;
        margin: 0;
        box-sizing: border-box;
    }

    body {
        background: #D9E4F5;
        font-family: 'Macondo', cursive;
        font-size: 16px;
    }

    .container {
      text-align: center;
    }
    .vue-logo {
      height: 12.5rem;
      width: 12.5rem;
      margin-top: 1rem;
    }
    .content {
      margin-top: 1.5rem;
      height: 5rem;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .content > input {
      width: 12.5rem;
      height: 1.875rem;
      margin-right: 5px;
    }
    .content > button {
      width: 3.75rem;
      height: 2rem;
      font-family: 'Macondo', cursive;
      font-weight: bold;
      color: white;
      background: green;
      border: none;
      
    }

    .container > h1 {
      color: green;
    }

    @media only screen and (min-width: 600px) {
        .content > input {
          width: 18.75rem;
     
    }
  }
</style>
