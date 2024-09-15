<template>
  <!-- ToDoList.vue -->
  <div class="todo-list">
    <ToDoItem
      v-for="(item, index) in items"
      :key="index"
      :title="item.title"
      :description="item.description"
    />
  </div>
</template>

<script>
import ToDoItem from './ToDoItem.vue';

export default {
  name: 'ToDoList',
  components: {
    ToDoItem,
  },
  props: {
    items: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="less" scoped>
.todo-list {
  flex: 1;
  .todo-item {
    background-color: gray;
    min-height: 70px;
    margin: 10px;
    padding: 10px;
    color: white;
    border-radius: 8px;
    font-size: 2rem;
    .todo-item-content-title {
      font-weight: bold;
    }
    .todo-item-content-description {
      font-size: 1.5rem;
    }
  }
}
</style>
