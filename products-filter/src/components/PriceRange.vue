<template>
  <div>
    <h3>Фильтр по цене</h3>
    <label>
      От: <input v-model.number="minPrice" type="number" min="0" />
    </label>
    <label>
      До: <input v-model.number="maxPrice" type="number" :min="minPrice" />
    </label>
  </div>
</template>

<script setup lang="ts">
import { ref, watch } from "vue";

const minPrice = ref(0);
const maxPrice = ref(18000);

const emit = defineEmits<{
  (e: "updatePrice", value: { min: number; max: number }): void;
}>();

watch([minPrice, maxPrice], ([newMin, newMax]) => {
  emit("updatePrice", { min: newMin, max: newMax });
});
</script>