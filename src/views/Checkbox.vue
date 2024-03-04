<script setup>
import { ref } from "vue";
import Checkbox from "@/components/Checkbox/Checkbox.vue";
const checkboxActive = ref(true);
const checkboxDisabled = ref(true);
const checkboxDisabledChecked = ref(true);
</script>

<template>
  <h1 class="heading-1">Checkbox</h1>
  <h2 class="heading-2">Checkbox Active</h2>
  <div class="line">
    <checkbox
      label="Checkbox Active"
      id="checkboxActive"
      name="checkboxActive"
      value="I like it"
      v-model:checked="checkboxActive"
    />
  </div>
  <h2 class="heading-2">Checkbox Disabled</h2>
  <div class="line">
    <checkbox
      label="Checkbox Disabled"
      id="checkboxDisabled"
      name="checkboxDisabled"
      value="I like it"
      :disabled="checkboxDisabled"
      v-model:checked="checkboxDisabledChecked"
    />
  </div>
</template>