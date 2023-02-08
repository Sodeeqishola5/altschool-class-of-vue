<template>
  <div id="composable">
    <div class="container">
      <h1>Color Picker Game</h1>
      <div class="color-display" :style="{ backgroundColor: selectedColor }"></div>
      <div class="color-options">
        <div
          class="color-option"
          v-for="color in colors"
          :key="color"
          :style="{ backgroundColor: color }"
          @click="selectColor(color)"
        ></div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue';

export default {
  setup() {
    const colors = ref(["red", "blue", "green", "yellow"]);
    const selectedColor = ref("red");

    function selectColor(color) {
      selectedColor.value = color;
    }

    onMounted(() => {
      console.log('mounted');
    });

    return {
      colors,
      selectedColor,
      selectColor
    };
  }
};
</script>

<style>
#composable {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.container {
  max-width: 600px;
  margin: 50px auto;
}

.color-display {
  height: 200px;
  width: 100%;
  border: 1px solid #ccc;
  margin-bottom: 20px;
}

.color-options {
  display: flex;
  flex-wrap: wrap;
}

.color-option {
  height: 50px;
  width: 25%;
  cursor: pointer;
}
</style>
