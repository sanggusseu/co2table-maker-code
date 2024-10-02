<template>
  <form @submit.prevent="" class="flex">
    <q-input
      type="number"
      min="1"
      v-model="store.record"
      label="숨 참기 최고 기록 (초)"
      :onkeydown="handleOnkeyDown"
    />
  </form>
</template>

<script setup>
import { useRecordStore } from 'src/stores/record';
const store = useRecordStore();

const handleOnkeyDown = e => {
  const num = e.key * 1;
  const exclude = ['Backspace', 'Delete', '.'];
  if (exclude.includes(e.key)) return;
  if (isNaN(num)) e.preventDefault();
};
</script>

<style lang="scss" scoped></style>
