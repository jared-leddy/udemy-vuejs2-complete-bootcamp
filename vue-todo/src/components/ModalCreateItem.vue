<template>
  <div>
    <div
      class="app-button"
      @click="isModalOpen = true"
    >
      Create
    </div>
    <div
      class="modal"
      :class="{ 'modal--active': isModalOpen }"
    >
      <div class="modal-content">
        <span
          class="close"
          @click="isModalOpen = false"
        >
          &times;
        </span>
        <slot></slot>
        <!-- Ensure this slot is properly used -->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ModalCreateItem',
  data() {
    return {
      isModalOpen: false,
    };
  },
};
</script>

<style scoped lang="less">
.close {
  color: #aaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
  line-height: 8px;
  &:hover {
    cursor: pointer;
  }
}

.modal {
  display: none;
  position: fixed;
  z-index: 999;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgba(0, 0, 0, 0.75);
  &--active {
    display: block;
  }
  &-content {
    background-color: #fefefe;
    margin: 15% auto;
    width: 50%;
    padding: 20px;
    border: 1px solid #888;
  }
}
</style>
