<script setup lang="ts">
import { ref } from "vue";
const selectedType = ref(1);

const pokeTypes = [
  { value: 1, name: "くさ" },
  { value: 2, name: "みず" },
  { value: 3, name: "ほのお" },
];
</script>
<template>
  <div class="radio">
    <label v-for="pokeType in pokeTypes" :key="pokeType.value">
      <input type="radio" name="selectedType" :value="pokeType.value" v-model="selectedType">
      {{ pokeType.name }}
    </label>
    <p>radio: {{ selectedType }}</p>
  </div>
</template>