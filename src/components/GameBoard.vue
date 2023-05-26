<template>
  <div class="game-board">
    <div class="game-courts">
      <div
        v-for="(courtRow, index) in courts"
        :key="index"
        class="game-courts__row"
      >
        <button
          v-for="(court, idx) in courtRow"
          :key="idx"
          class="court"
          :disabled="court.length"
          @click="$emit('clicked')"
        >
          {{ court }}
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  setup() {
    const courts = ref([]);
    courts.value = [
      ["", "", ""],
      ["", "", ""],
      ["", "", ""],
    ];
    return { courts };
  },
};
</script>

<style>
.game-courts {
  display: flex;
  flex-direction: column;
  border: 1px solid #333;
}
.game-courts__row {
  display: flex;
}

.game-courts__row:not(:last-child) {
  border-bottom: 1px solid #333;
}

.court {
  width: 80px;
  height: 80px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: background 0.3s ease;
  border: none;
  background: #fff;
}

.court:hover,
.court:disabled {
  background-color: #eee;
}

.court:not(:last-child) {
  border-right: 1px solid #333;
}
</style>
