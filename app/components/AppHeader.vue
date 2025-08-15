<script setup lang="ts">
const route = useRoute()

const items = computed(() => [{
  label: 'Blog',
  to: '/blog',
  active: route.path.startsWith('/blog')
}])
</script>

<template>
  <UHeader>
    <template #left>
      <NuxtLink to="/">
        <LogoPro class="w-auto h-6 shrink-0" />
      </NuxtLink>
      <TemplateMenu />
    </template>

    <UNavigationMenu
      :items="items"
      variant="link"
    />

    <template #right>
      <UColorModeButton />
    </template>

    <template #body>
      <UNavigationMenu
        :items="items"
        orientation="vertical"
        class="-mx-2.5"
      />

      <USeparator class="my-6" />
    </template>
  </UHeader>
</template>
