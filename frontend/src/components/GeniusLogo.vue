<template>
  <svg
    class="genius-logo-svg"
    viewBox="0 0 220 140"
    xmlns="http://www.w3.org/2000/svg"
    role="img"
    :aria-label="label"
  >
    <defs>
      <linearGradient id="geniusTechGrad" x1="24" y1="24" x2="196" y2="116" gradientUnits="userSpaceOnUse">
        <stop stop-color="#0284c7" />
        <stop offset="1" stop-color="#4f46e5" />
      </linearGradient>
    </defs>
    <rect x="4" y="4" width="212" height="132" rx="20" fill="#f8fafc" stroke="#cbd5e1" stroke-width="2" />
    <!-- pin traces -->
    <g stroke="#94a3b8" stroke-width="2" stroke-linecap="round" fill="none">
      <path d="M12 44h18M12 70h18M12 96h18M190 44h18M190 70h18M190 96h18" />
      <path d="M44 12v18M70 12v18M96 12v18M124 12v18M150 12v18M176 12v18" />
      <path d="M44 110v18M70 110v18M96 110v18M124 110v18M150 110v18M176 110v18" />
    </g>
    <!-- subtle grid -->
    <g fill="#e2e8f0" opacity="0.85">
      <circle v-for="gx in gridXs" :key="'g'+gx" :cx="gx" cy="32" r="1.2" />
      <circle v-for="gx in gridXs" :key="'g2'+gx" :cx="gx" cy="108" r="1.2" />
    </g>
    <!-- chip -->
    <rect x="72" y="46" width="76" height="48" rx="8" fill="url(#geniusTechGrad)" />
    <g stroke="#e0f2fe" stroke-width="2.2" stroke-linecap="round" opacity="0.92">
      <path d="M88 62h44M88 70h44M88 78h32" />
    </g>
    <circle cx="110" cy="88" r="4" fill="#e0f2fe" opacity="0.95" />
    <!-- signal arcs -->
    <path
      d="M32 70 Q56 52 72 62"
      fill="none"
      stroke="#38bdf8"
      stroke-width="1.5"
      stroke-dasharray="4 6"
      opacity="0.55"
    />
    <path
      d="M188 70 Q164 88 148 78"
      fill="none"
      stroke="#818cf8"
      stroke-width="1.5"
      stroke-dasharray="4 6"
      opacity="0.55"
    />
  </svg>
</template>

<script setup>
defineProps({
  label: { type: String, default: 'Genius' }
})

const gridXs = [52, 76, 100, 124, 148, 172]
</script>

<style scoped>
.genius-logo-svg {
  width: 100%;
  max-width: 440px;
  height: auto;
  display: block;
}
</style>
