<script setup lang="ts">
import SignupForm from '../components/signup/SignupForm.vue'
import SignupTestimonial from '../components/signup/SignupTestimonial.vue'
</script>

<template>
  <main class="grid min-h-screen place-items-center bg-[#f1f1f3] p-3 font-['Inter',Arial,sans-serif] text-[#171717] min-[421px]:p-5 min-[721px]:p-12">
    <section
      class="grid min-h-0 w-full grid-cols-1 overflow-hidden rounded-xl bg-white shadow-[0_28px_55px_rgba(38,35,50,0.13)] min-[501px]:max-[720px]:w-[500px] min-[721px]:min-h-[min(75vh,720px)] min-[721px]:max-w-[1200px] min-[721px]:grid-cols-[1fr_2fr]"
      aria-label="Create your Nucleus account"
    >
      <SignupTestimonial />
      <SignupForm />
    </section>
  </main>
</template>
