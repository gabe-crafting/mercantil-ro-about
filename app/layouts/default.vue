<script setup lang="ts">
const runtimeConfig = useRuntimeConfig()
const items = computed(() => [
  { label: 'Home', href: `${runtimeConfig.public.mercantilRoLink}/`, external: true },
  {
    label: 'Shops',
    href: `${runtimeConfig.public.mercantilRoLink}/shops`,
    external: true
  },
  {
    label: 'About Us',
    to: '/'
  }])
</script>

<template>
  <div>
    <UHeader title="Mercantil.RO">
      <template #title>
        <UIcon name="healthicons:market-stall" size="30" />
        <h1>Mercantil.RO</h1>
      </template>
      <template #default>
        <UNavigationMenu :items="items" variant="link" />
      </template>
      <template #right>
        <UColorModeButton />
      </template>
    </UHeader>
    <UMain>
      <slot />
    </UMain>
    <AppFooter />
  </div>
</template>
