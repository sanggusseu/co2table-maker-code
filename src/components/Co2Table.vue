<template>
  <div class="q-mt-md">
    <q-table
      title="CO2 Table"
      :rows="rows"
      :columns="columns"
      row-key="name"
      rows-per-page-options="0"
      hide-bottom
    />
  </div>
</template>

<script setup>
const props = defineProps({
  rows: Array,
  columns: Array,
});
</script>

<style lang="scss" scoped></style>
