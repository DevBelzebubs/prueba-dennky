<script setup lang="ts">
import { onBeforeUnmount, onMounted, ref, watch } from 'vue'

const isOpen = defineModel<boolean>({ required: true })
const closeButton = ref<HTMLButtonElement>()

const closeModal = () => (isOpen.value = false)

watch(isOpen, (open) => open && closeButton.value?.focus(), { flush: 'post' })

const handleKeydown = (e: KeyboardEvent) => {
  if (e.key === 'Escape' && isOpen.value) closeModal()
}

onMounted(() => window.addEventListener('keydown', handleKeydown))
onBeforeUnmount(() => window.removeEventListener('keydown', handleKeydown))
</script>

<template>
  <Teleport to="body">
    <div v-if="isOpen" class="fixed inset-0 z-50 grid place-items-center bg-black/50 p-4" @click.self="closeModal">
      <section aria-labelledby="signup-modal-title" aria-modal="true"
        class="w-full max-w-sm rounded-2xl bg-white p-6 shadow-2xl" role="dialog">
        <h2 id="signup-modal-title" class="text-lg font-semibold text-[#171717]">
          Missing information
        </h2>
        <p class="mt-2 text-sm text-gray-600">
          Please complete all required fields before creating your account.
        </p>
        <div class="mt-6 flex justify-end">
          <button ref="closeButton"
            class="rounded-full bg-[#7354f8] px-5 py-2 text-sm font-semibold text-white transition hover:bg-[#6242e9] focus:outline-none focus:ring-2 focus:ring-[#7354f8] focus:ring-offset-2"
            type="button" @click="closeModal">
            Got it
          </button>
        </div>
      </section>
    </div>
  </Teleport>
</template>
