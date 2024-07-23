<template>
  <ModalCreateItem ref="modal">
    <form
      class="app-form"
      @submit.prevent="submitFormHandler"
    >
      <div class="form-control">
        <label class="label">Title</label>
        <input
          v-model="formData.title"
          class="form-input"
          type="text"
        />
      </div>
      <div class="form-control">
        <label class="label">Description</label>
        <textarea
          v-model="formData.description"
          class="form-input"
          cols="30"
          rows="5"
        ></textarea>
      </div>
      <button
        type="submit"
        class="app-button isPrimary"
        @click="createToDoItem"
      >
        Submit
      </button>
    </form>
  </ModalCreateItem>
</template>

<script>
import ModalCreateItem from './ModalCreateItem.vue';

export default {
  name: 'FormCreateToDoItem',
  components: {
    ModalCreateItem,
  },
  data() {
    return {
      formData: {
        title: '',
        description: '',
      },
    };
  },
  methods: {
    submitFormHandler() {
      console.log(this.formData);
      this.$refs.modal.isModalOpen = false; // Close modal after submission
    },
  },
};
</script>

<style scoped lang="less">
.app-form {
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
</style>
