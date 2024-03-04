<script setup>
import { ref } from "vue";
import Radiobutton from "@/components/Radiobutton.vue";

const cities = ref([
  { name: "Moscow", id: "id1" },
  { name: "Petersburg", id: "id2" },
  { name: "Kazan", id: "id3" },
  { name: "New-York", id: "id4" },
]);

const selectedCity = ref("Kazan");

const disabledRadio = ref(true);
const disabledRadioChecked = ref(true);
</script>

<template>
  <h1 class="heading-1">Radiobutton</h1>
  <h2 class="heading-2">Basic</h2>
  <div class="line line--block">
    <p>Selected: {{ selectedCity }}</p>
    <div v-for="city in cities" :key="city.id">
      <radiobutton
        :value="city.name"
        :label="city.name"
        :id="city.id"
        :checked="selectedCity === city.name"
        name="city"
        v-model:checkedValue="selectedCity"
      />
    </div>
  </div>
  <h2 class="heading-2">Disabled</h2>
  <div class="line">
    <radiobutton
      value="Radiobutton Disabled"
      label="Radiobutton Disabled"
      id="radiobuttonDisabled"
      name="radiobuttonDisabled"
      :disabled="disabledRadio"
      v-model:checkedValue="disabledRadioChecked"
    />
  </div>
</template>