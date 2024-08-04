<template>
  <div class="mt-24 ml-10">
    <div class="text-xl">Tasks</div>
    <!-- <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-20"></div>
      -->
    <button class="btn btn-md btn-secondary" @click="addColumn('New column')">Add Column</button>
    <div class="flex-1 flex gap-4 px-3 overflow-x-auto">
      <Column v-for="column of STORE" :key="column.columnId" :column="column" />
    </div>
  </div>
</template>

<script setup lang="ts">
import { onMounted } from 'vue'
import Column from '@/components/Column.vue'
import { STORE, addColumn } from '@/stores/kanbanStore'

onMounted(async () => {
  console.log(STORE)
  if (STORE.value.length === 0) await addColumn('To Do')
})
</script>
