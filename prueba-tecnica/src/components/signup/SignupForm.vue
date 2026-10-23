<script setup lang="ts">
import { ref, watch } from 'vue'

const name = ref('')
const email = ref('')
const password = ref('')
const confirmPassword = ref('')
const confirmationInput = ref<HTMLInputElement | null>(null)

watch([password, confirmPassword], ([currentPassword, currentConfirmation]) => {
  confirmationInput.value?.setCustomValidity(
    currentConfirmation && currentPassword !== currentConfirmation ? 'Passwords do not match.' : '',
  )
})
</script>
<template>
  <div class="grid min-w-0 place-items-center bg-white px-6 py-8 min-[721px]:p-10">
    <div class="w-full max-w-[330px]">
      <header class="mb-[22px] text-center">
        <h1 class="mb-1 text-[21px] font-bold tracking-[-0.04em] text-[#171717]">
          Create your account
        </h1>
        <p class="text-[11px] text-[#858585]">Join Nucleus UI and start designing with ease.</p>
      </header>
      <form class="grid gap-[10px]" @submit.prevent>
        <label
          class="grid min-h-[42px] content-center rounded-lg border border-[#e8e8e8] bg-white px-[11px] py-1 transition focus-within:border-[#7655ff] focus-within:shadow-[0_0_0_3px_rgba(118,85,255,0.2)]">
          <span class="text-[9px] leading-tight text-[#999]">Name</span>
          <input v-model="name"
            class="min-w-0 border-0 bg-transparent py-px text-xs text-[#222] outline-none placeholder:text-[#999]"
            autocomplete="name" name="name" placeholder="Alex Jordan" required />
        </label>
        <label
          class="grid min-h-[42px] content-center rounded-lg border border-[#e8e8e8] bg-white px-[11px] py-1 transition focus-within:border-[#7655ff] focus-within:shadow-[0_0_0_3px_rgba(118,85,255,0.2)]">
          <span class="text-[9px] leading-tight text-[#999]">Email</span>
          <input v-model="email"
            class="min-w-0 border-0 bg-transparent py-px text-xs text-[#222] outline-none placeholder:text-[#999]"
            autocomplete="email" name="email" placeholder="alex.jordan@gmail.com" required type="email" />
        </label>
        <label
          class="grid min-h-[42px] content-center rounded-lg border border-[#e8e8e8] bg-white px-[11px] py-1 transition focus-within:border-[#7655ff] focus-within:shadow-[0_0_0_3px_rgba(118,85,255,0.2)]">
          <span class="text-[9px] leading-tight text-[#999]">Password</span>
          <input v-model="password" class="min-w-0 border-0 bg-transparent py-px text-xs text-[#222] outline-none placeholder:text-[#999]" autocomplete="new-password" minlength="8" name="password" placeholder="Enter your password" required type="password" />
        </label>
        <label
          class="grid min-h-[42px] content-center rounded-lg border border-[#e8e8e8] bg-white px-[11px] py-1 transition focus-within:border-[#7655ff] focus-within:shadow-[0_0_0_3px_rgba(118,85,255,0.2)]">
          <span class="text-[9px] leading-tight text-[#999]">Confirm password</span>
          <input ref="confirmationInput" v-model="confirmPassword"
            class="min-w-0 border-0 bg-transparent py-px text-xs text-[#222] outline-none placeholder:text-[#999]"
            autocomplete="new-password" name="confirm-password" placeholder="Confirm password" required
            type="password" />
        </label>

        <button
          class="mt-[5px] flex min-h-11 w-full items-center justify-center rounded-full bg-[#7354f8] text-[11px] font-semibold text-white transition hover:bg-[#6242e9] active:translate-y-px cursor-pointer"
          type="submit">
          Create account
        </button>
      </form>

      <div class="my-5 flex items-center gap-3 text-[10px] text-[#858585]" aria-hidden="true">
        <span class="h-px flex-1 bg-[#ededed]"></span>
        <span>OR</span>
        <span class="h-px flex-1 bg-[#ededed]"></span>
      </div>

      <button
        class="relative flex min-h-11 w-full items-center justify-center rounded-full bg-[#f4f5f7] text-[11px] font-semibold text-[#222] transition hover:bg-[#eceef1] cursor-pointer"
        type="button">
        <svg class="absolute left-3 h-[19px] w-[19px]" viewBox="0 0 48 48" aria-hidden="true">
          <path fill="#4285F4"
            d="M43.6 24.5c0-1.4-.1-2.8-.4-4.1H24v7.8h11a9.4 9.4 0 0 1-4.1 6.2v5.1h6.6c3.9-3.6 6.1-8.8 6.1-15Z" />
          <path fill="#34A853"
            d="M24 44c5.5 0 10.1-1.8 13.5-4.9l-6.6-5.1c-1.8 1.2-4 2-6.9 2-5.3 0-9.8-3.6-11.4-8.4H5.8v5.3A20 20 0 0 0 24 44Z" />
          <path fill="#FBBC05" d="M12.6 27.6a12 12 0 0 1 0-7.2v-5.3H5.8a20 20 0 0 0 0 17.8l6.8-5.3Z" />
          <path fill="#EA4335"
            d="M24 12c3 0 5.7 1 7.8 3.1l5.8-5.8C34.1 6 29.5 4 24 4A20 20 0 0 0 5.8 15.1l6.8 5.3C14.2 15.6 18.7 12 24 12Z" />
        </svg>
        <span>Sign up with Google</span>
      </button>

      <p class="mt-[25px] text-center text-[10px] text-[#8a8a8a]">
        Have an account?
        <a class="font-semibold text-[#7354f8] no-underline hover:underline" href="#login">Log in</a>
      </p>
    </div>
  </div>
</template>
