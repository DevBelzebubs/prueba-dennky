<template>
  <aside class="relative min-h-[220px] min-w-0 overflow-hidden bg-[#51463f] text-white min-[721px]:min-h-0">
    <div
      class="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1524504388940-b1c1722653e1?auto=format&fit=crop&w=1200&q=85')] bg-cover bg-center"
      role="img"
      aria-label="Woman working at her laptop"
    ></div>
    <div class="absolute inset-0 bg-[linear-gradient(180deg,rgba(0,0,0,0.3)_0%,transparent_34%,rgba(0,0,0,0.66)_100%)]"></div>

    <a
      class="absolute left-5 top-5 z-10 inline-flex items-center gap-2 text-lg font-bold tracking-[-0.04em] text-white no-underline min-[721px]:left-7 min-[721px]:top-7"
      href="/"
      aria-label="Nucleus home"
    >
      <img class="h-[18px] w-[18px] object-contain" src="/img/logo.png" alt="" />
      <span>Nucleus</span>
    </a>

    <figure class="absolute bottom-[18px] left-5 right-5 z-10 m-0 min-[721px]:bottom-[26px] min-[721px]:left-7 min-[721px]:right-[25px]">
      <blockquote class="mb-3 text-[21px] font-bold leading-tight tracking-[-0.03em] min-[721px]:mb-[18px] min-[721px]:text-[clamp(20px,2.1vw,26px)]">
        “Simply all the tools that<br class="hidden min-[721px]:inline" /> my team and I need.”
      </blockquote>
      <figcaption class="grid gap-1 text-xs">
        <strong class="font-bold">Karen Yue</strong>
        <span class="text-[11px]">Director of Digital Marketing Technology</span>
      </figcaption>
    </figure>
  </aside>
</template>
