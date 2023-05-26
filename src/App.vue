<template>
  <div class="wrapper">
    <h2 class="title">Tic-Tac-Toe</h2>
    <main>
      <GameSidebar :next="activePlayer" :winner="winner" />
      <GameBoard :courts="courts" @selected="selectCourt" />
      <StepsBar />
    </main>
  </div>
</template>

<script setup>
import GameSidebar from "./components/GameSidebar";
import GameBoard from "./components/GameBoard";
import StepsBar from "./components/StepsBar";

import { ref, computed } from "vue";

const courts = ref([
  ["", "", ""],
  ["", "", ""],
  ["", "", ""],
]);
const winner = ref("");

const flag = ref(true);
const activePlayer = computed(() => {
  return flag.value ? "X" : "O";
});
const selectCourt = (index, idx) => {
  courts.value[index][idx] = activePlayer.value;
  flag.value = !flag.value;
};
</script>

<style>
*,
*::before,
*::after {
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

main {
  margin-top: 40px;
  display: flex;
  max-width: 1000px;
  margin-inline: auto;
  justify-content: space-between;
}
</style>
