<template>
  <div class="app">
    <p>
      <!-- interpolation -->
      {{ name }} - {{ age }}
      <button @click="changeName('hayfa')">change Name</button>
      <button @click="changeAge(70)">change Age</button>
    </p>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "App",
  setup() {
    // use ref , toRefs reactive : compostion Api
    const name = ref("Link");
    // use generic variables
    const age = ref<String | number>(25);

    const changeName = (newName: string) => {
      name.value = newName;
      return newName;
    };

    const changeAge = (newAge: number) => {
      age.value = newAge;
      return newAge;
    };

    return { name, age, changeName, changeAge };
  },
});
</script>

<style>
</style>
