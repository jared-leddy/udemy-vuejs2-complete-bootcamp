<template>
  <div id="app">
    <div class="todo-wrapper">
      <div class="todo-container">
        <div class="todo-list">
          <div class="todo-item">
            <div class="todo-item-content">
              <div class="todo-item-content-title">Walk the dog</div>
              <div class="todo-item-content-description">Go to the forest near the zoo.</div>
            </div>
          </div>
          <div class="todo-item">
            <div class="todo-item-content">
              <div class="todo-item-content-title">Buy some bread</div>
              <div class="todo-item-content-description">Whole grain bread would be good.</div>
            </div>
          </div>
          <div class="todo-item">
            <div class="todo-item-content">
              <div class="todo-item-content-title">Learn programming</div>
              <div class="todo-item-content-description">Starting tomorrow would be best.</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import playground from './playground.js';

export default {
  name: 'App',
  // function run automatically
  created() {
    playground();
  },
};
</script>

<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.todo {
  &-wrapper {
    display: flex;
    justify-content: center;
    width: 100%;
  }

  &-container {
    width: 400px;
    min-height: 400px;
    background-color: #ededed;
    border-radius: 8px;
  }
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
