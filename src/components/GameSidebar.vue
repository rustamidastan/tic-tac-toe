<template>
  <div class="sidebar">
    <h4 class="sidebar__next-player">Next player {{ props.next }}</h4>
    <button class="sidebar__btn">Restart</button>
    <h3 v-if="props.winner.length" class="sidebar__next-player">
      Winner {{ props.winner }}
    </h3>
  </div>
</template>

<script setup>
import { defineProps } from "vue";
const props = defineProps(["next", "winner"]);
</script>

<style></style>
