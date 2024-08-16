<template>
  <form @submit.prevent="" class="flex">
    <q-input
      type="number"
      min="1"
      v-model="store.record"
      label="숨 참기 최고 기록 (초)"
    />
  </form>
</template>

<script setup>
import { useRecordStore } from 'src/stores/record';

const store = useRecordStore();
</script>

<style lang="scss" scoped></style>
