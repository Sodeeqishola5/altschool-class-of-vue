<script>
import ColorPickerGame from "./components/ColorPickerGame.vue";
import Recap_01_02_2023 from "./components/Recap_01_02_2023.vue";
import Composable from "./composables/Composable.vue";

export default {
  components: { Composable, ColorPickerGame, Recap_01_02_2023 },
  data() {
    return {
      currentLesson: "color-picker-game",
    };
  },
};
</script>

<template>
  <div>
    <Composable/>
    <ColorPickerGame v-if="currentLesson === 'color-picker-game'" />
    <Recap_01_02_2023 v-else />
  </div>
</template>

<style scoped></style>
