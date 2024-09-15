<template>
  <div>
    <div
      class="todo-item"
      v-if="!isEditMode"
    >
      <div class="todo-item-content">
        <div class="todo-item-content-title">{{ title }}</div>
        <div class="todo-item-content-description">{{ description }}</div>
      </div>
      <button
        class="app-button isWarning"
        @click="editToDoItem"
      >
        Edit
      </button>
      <button
        class="app-button isDanger"
        @click="deleteToDoItem"
      >
        Delete
      </button>
    </div>
    <div v-else>
      <form
        class="app-form"
        @submit.prevent="submitFormHandler"
      >
        <div class="form-control">
          <label class="label">Title</label>
          <input
            class="form-input"
            v-model="localTitle"
            type="text"
          />
        </div>
        <div class="form-control">
          <label class="label">Description</label>
          <textarea
            v-model="localDescription"
            class="form-input"
            cols="30"
            rows="5"
          ></textarea>
        </div>
        <button
          type="submit"
          class="app-button isWarning"
        >
          Update
        </button>
        <button
          type="button"
          class="app-button isDanger"
          @click="cancelEditToDoItem"
        >
          Cancel
        </button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ToDoItem',
  data() {
    return {
      isEditMode: false,
      localTitle: this.title,
      localDescription: this.description,
    };
  },
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
  methods: {
    cancelEditToDoItem() {
      this.isEditMode = false;
      this.localTitle = this.title;
      this.localDescription = this.description;
    },
    deleteToDoItem() {
      this.$emit('delete-todo', {
        title: this.localTitle,
        description: this.localDescription,
      });
    },
    editToDoItem() {
      this.isEditMode = true;
    },
    submitFormHandler() {
      this.$emit('update-todo', {
        title: this.localTitle,
        description: this.localDescription,
      });
      this.isEditMode = false;
    },
  },
  watch: {
    title(newVal) {
      this.localTitle = newVal;
    },
    description(newVal) {
      this.localDescription = newVal;
    },
  },
};
</script>

<style lang="less" scoped>
@red: red;
@darkGray: #2c3e50;
@lightGray: #ededed;

.app-form {
  text-align: left;
  margin: 10px;
}
.app-button {
  border-color: white;
  font-size: 1rem;
  margin: 10px 10px 10px 0;
  &:hover {
    color: white;
  }
}

.todo {
  &-item {
    background-color: gray;
    min-height: 70px;
    margin: 10px;
    padding: 10px;
    color: white;
    border-radius: 8px;
    font-size: 2rem;
    text-align: left;
    &-content-title {
      font-weight: bold;
    }
    &-content-description {
      font-size: 1.5rem;
    }
  }
}
</style>
