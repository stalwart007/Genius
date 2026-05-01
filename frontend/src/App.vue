<template>
  <router-view />
</template>

<script setup>
import { watch } from 'vue'
import { useI18n } from 'vue-i18n'

const { t, locale } = useI18n()

watch(
  () => [locale.value, t('meta.title'), t('meta.description')],
  () => {
    document.title = t('meta.title')
    const meta = document.querySelector('meta[name="description"]')
    if (meta) meta.setAttribute('content', t('meta.description'))
  },
  { immediate: true }
)
</script>

<style>
/* Light theme tokens (shared across pages) */
:root {
  --gf-bg: #f8fafc;
  --gf-surface: #ffffff;
  --gf-text: #1e293b;
  --gf-text-muted: #64748b;
  --gf-accent: #2563eb;
  --gf-accent-hover: #1d4ed8;
  --gf-accent-soft: #eff6ff;
  --gf-border: #e2e8f0;
}

/* 全局样式重置 */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: 'JetBrains Mono', 'Space Grotesk', system-ui, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: var(--gf-text);
  background-color: var(--gf-bg);
}

/* 滚动条样式 */
::-webkit-scrollbar {
  width: 8px;
  height: 8px;
}

::-webkit-scrollbar-track {
  background: #f1f5f9;
}

::-webkit-scrollbar-thumb {
  background: #cbd5e1;
}

::-webkit-scrollbar-thumb:hover {
  background: #94a3b8;
}

/* 全局按钮样式 */
button {
  font-family: inherit;
}
</style>
