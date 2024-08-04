<template>
  <dialog
    id="my_modal_20"
    v-if="isModalActive"
    class="modal sm:modal-middle"
    :class="{ 'modal-open': isModalActive }"
  >
    <div class="modal-box">
      <button
        class="btn btn-sm btn-circle btn-ghost absolute right-2 top-2"
        @click="$emit('close-modal')"
      >
        <span>x</span>
      </button>
      <h1 class="font-bold text-2xl">{{ heading }}</h1>

      <div v-if="isModalActive" class="p-1">
        <slot />
      </div>
    </div>
  </dialog>
</template>

<script setup lang="ts">
defineEmits(['close-modal'])

defineProps<{
  isModalActive: boolean
  heading: string
}>()
</script>
