<template>
  <div>
    <div>
      <CallToAction />
    </div>
    <div :class="mainDivClass">
      <div>
        <span class="pr-1 font-medium">This is a HMR test, try changing the color:</span>
        <span class="text-blue-500">meow!</span>
      </div>
      <p class="text-brand">
        This color comes from the `./tailwind.config`
      </p>
      <p class="text-secondary">
        This color comes from the `./theme` layer
      </p>
      <p class="text-accent">
        This color comes from the `./modules/template` module
      </p>
      <p class="text-zeroLayer">
        This color comes from the `tailwindcss:loadConfig` hook
      </p>
      <p class="text-twConfig">
        This color comes from the `tailwindcss:config` hook
      </p>
      <div>
        <NuxtLink
          to="/content"
          class="underline hover:text-indigo-500"
        >
          Visit the /content page to check out the @nuxt/content integration!
        </NuxtLink>
      </div>
      <div>
        <span class="text-sm font-semibold text-gray-700">Resolved tailwind config:</span>
        <textarea
          class="p-4 block text-sm border border-gray-100 rounded shadow w-full h-[32rem] font-mono outline-none"
          readonly
          :value="JSON.stringify(tailwindConfig, null, 2)"
        />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { tw } from '#imports'
import tailwindConfig from '#tailwind-config'

// const tw = <T>(s: T) => s
const mainDivClass = tw`max-w-screen-lg p-4 mx-auto space-y-4`
</script>
