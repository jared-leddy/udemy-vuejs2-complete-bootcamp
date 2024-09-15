<template>
  <div id="app">
    <h1>Next Lesson: 43</h1>
    <div class="todo-wrapper">
      <div class="todo-container">
        <ToDoList :items="todoItems" />
        <div class="todo-create-btn-container">
          <FormCreateToDoItem @formSubmitted="createToDoItem" />
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
  data() {
    return {
      todoItems: [
        {
          title: 'Walk the dog',
          description: 'Go to the forest near the zoo.',
        },
        {
          title: 'Buy some bread',
          description: 'Whole grain bread would be good.',
        },
        {
          title: 'Learn programming',
          description: 'Starting tomorrow would be best.',
        },
      ],
    };
  },
  created() {
    playground();
  },
  methods: {
    createToDoItem(item) {
      this.todoItems.push(item);
    },
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
.isWarning {
  background-color: #ffa753 !important;
}
.isDanger {
  background-color: #ff5a5a !important;
}

.app {
  &-button {
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
  &-error {
    color: red;
  }
  &-form {
    .label {
      display: block;
      font-size: 1.25em;
      font-weight: bold;
    }
    .form-input {
      padding: 10px;
      font-size: 1.2em;
    }
    .form-control {
      margin-bottom: 10px;
    }
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
