<script setup lang="ts">
import { ref } from "vue";

const inputName = ref("フシギダネ");
</script>

<template>
  <div class="input">
    <input type="text" v-model="inputName"/>
    <p>input: {{ inputName }}</p>
  </div>
</template>
