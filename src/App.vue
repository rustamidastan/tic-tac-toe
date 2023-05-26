<template>
  <div class="wrapper">
    <h2 class="title">Tic-Tac-Toe</h2>
    <main>
      <GameSidebar />
      <GameBoard />
      <StepsBar />
    </main>
  </div>
</template>

<script>
import GameSidebar from "./components/GameSidebar";
import GameBoard from "./components/GameBoard";
import StepsBar from "./components/StepsBar";
export default {
  name: "App",
  components: { GameSidebar, GameBoard, StepsBar },
};
</script>

<style>
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
