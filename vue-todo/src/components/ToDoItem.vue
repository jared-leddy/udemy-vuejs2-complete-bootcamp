<template>
  <!-- ToDoItem.vue -->
  <div class="todo-item">
    <div class="todo-item-content">
      <div class="todo-item-content-title">{{ title }}</div>
      <div class="todo-item-content-description">{{ description }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ToDoItem',
  props: {
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
  },
};
</script>

<style lang="less" scoped>
@red: red;
@darkGray: #2c3e50;
@lightGray: #ededed;

.todo {
  &-item {
    background-color: gray;
    min-height: 70px;
    margin: 10px;
    padding: 10px;
    color: white;
    border-radius: 8px;
    font-size: 2rem;
    &-content-title {
      font-weight: bold;
    }
    &-content-description {
      font-size: 1.5rem;
    }
  }
}
</style>
