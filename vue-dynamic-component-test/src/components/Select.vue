<script setup lang="ts">
import { ref } from "vue";
const selectedSkill = ref(1);

const pokeSkills = [
  { value: 1, name: "たいあたり" },
  { value: 2, name: "なきごえ" },
  { value: 3, name: "ひっかく" },
  { value: 4, name: "しっぽをふる" },
];
</script>

<template>
  <div class="select">
    <select v-model="selectedSkill">
      <option v-for="pokeSkill in pokeSkills" :value="pokeSkill.value" :key="pokeSkill.value">
        {{ pokeSkill.name }}
      </option>
    </select>
    <p>select: {{ selectedSkill }}</p>
  </div>
</template>
