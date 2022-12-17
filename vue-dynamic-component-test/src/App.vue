<script setup lang="ts">
import { ref } from "vue";
import Input from "@/components/Input.vue";
import Radio from "@/components/Radio.vue";
import Select from "@/components/Select.vue";

const currentComponent = ref(Input);
const currentComponentName = ref("Input");
let currentComponentIndex = 0;
const componentList = [
  { name: "Input", component: Input },
  { name: "Radio", component: Radio },
  { name: "Select", component: Select },
];

const onClick = () => {
  currentComponentIndex++;
  if (currentComponentIndex >= componentList.length) {
    currentComponentIndex = 0;
  }
  currentComponent.value = componentList[currentComponentIndex].component;
  currentComponentName.value = componentList[currentComponentIndex].name;
};
</script>

<template>
  <div id="app">
    <p>currentComponentName: {{ currentComponentName }}</p>
    <button @click="onClick">コンポーネント切り替え</button>
    <keep-alive>
      <component :is="currentComponent"/>
    </keep-alive>
  </div>
</template>
