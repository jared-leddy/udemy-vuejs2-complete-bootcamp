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
      <div class="app-error">
        <div class="form-error">
          {{ formError }}
        </div>
      </div>
      <button
        type="submit"
        class="app-button isPrimary"
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
      formError: '',
    };
  },
  computed: {
    isFormValid() {
      return this.formData.title.length > 8 && this.formData.description.length > 10 ? true : false;
    },
  },
  methods: {
    resetFormData() {
      this.formData = {
        title: '',
        description: '',
      };
    },
    submitFormHandler() {
      if (this.isFormValid) {
        this.formError = '';
        this.$refs.modal.isModalOpen = false; // Close modal after submission
        this.$emit('formSubmitted', { ...this.formData });
        this.resetFormData();
      } else {
        this.formError =
          'Form Error! Title needs to be longer than 8 characters and description longer than 10 characters.';
      }
    },
  },
};
</script>

<style scoped lang="less">
.form-error {
  margin: 1rem;
}
</style>
