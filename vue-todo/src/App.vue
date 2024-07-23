<template>
  <div id="app">
    <h1>Next Lesson: 43</h1>
    <div class="todo-wrapper">
      <div class="todo-container">
        <ToDoList />
        <div class="todo-create-btn-container">
          <FormCreateToDoItem />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import playground from './playground.js';
import FormCreateToDoItem from './components/FormCreateToDoItem.vue';
import ToDoList from './components/ToDoList.vue';

export default {
  name: 'App',
  components: {
    FormCreateToDoItem,
    ToDoList,
  },
  created() {
    playground();
  },
};
</script>

<style lang="less">
@red: red;
@darkGray: #2c3e50;
@lightGray: #ededed;

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: @darkGray;
  margin-top: 60px;
}

.isPrimary {
  background-color: green !important;
}

.app-button {
  font-size: 20px;
  padding: 10px;
  border-radius: 8px;
  border: solid 1px purple;
  background-color: purple;
  color: white;
  font-weight: bold;
  &:hover {
    cursor: pointer;
    background-color: white;
    color: purple;
  }
}

.todo {
  &-wrapper {
    display: flex;
    justify-content: center;
    width: 100%;
  }

  &-container {
    display: flex;
    flex-direction: column;
    width: 400px;
    min-height: 400px;
    background-color: @lightGray;
    border-radius: 8px;
  }
  &-create-btn-container {
    margin: 10px;
  }
}
</style>
