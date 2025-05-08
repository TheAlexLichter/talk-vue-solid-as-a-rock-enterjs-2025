---
theme: ./theme
title: "Vue - Solid as a Rock?"
website: lichter.io
handle: TheAlexLichter
favicon: https://lichter.io/img/me@2x.jpg
highlighter: shiki
lineNumbers: true
layout: intro
transition: fade
---

---
layout: intro
---

# Vue is <span class="underline text-red-500">boring</span>

---
layout: intro
---

# Vue is <span class="underline">boring</span> tech

---

# Vue is <span class="underline">boring</span> tech

* No drama

---

# Vue is <span class="underline">boring</span> tech

* ~~No~~ Little drama

<VClicks depth="2">

* It just works
* It's stable and reliable
* "One way" to do things, e.g. for:
  * Routing
  * State Management
* One main API to use (Composition API with `<script setup>` if compiler is used)
  * While still supporting Options API
* Steady improvements

</VClicks>

---
layout: intro
---

# Boring is <span class="underline text-green-500">good</span>


---
layout: intro
---


# <logos-vue/>ue - Solid as a Rock?


## Choosing Vue in 2025

<br><br>

### enterJS 2025

---
layout: two-cols
heading: About me
---

<template v-slot:default>
<div class="flex flex-col justify-center items-center h-full">
  <img class="w-75 rounded-full" src="https://lichter.io/img/me@2x.webp" />
  <h2 class="mt-4">Alexander Lichter</h2>
</div>
</template>

<template v-slot:right>
<VClicks class="space-y-2 mt-10 text-xl h-full">

* <VoidzeroIconsVoidzeroLogo class="text-white" width="4rem" height="auto" /> DevRel
* <mdi-account-check class="dark:text-green-100 text-green-700" /> **Web Engineering Consultant**
* <mdi-microphone /> Speaker & Instructor
* <logos-nuxt-icon /> Nuxt.js Team
* <mdi-github /><logos-bluesky class="text-sm mb-1 text-blue-400" /><mdi-youtube class="text-red-500" /><mdi-twitch class="text-purple-700" /> @TheAlexLichter
* <mdi-web /> [https://lichter.io](https://lichter.io)

</VClicks>
</template>

---

<img src="/angry.png" class="h-110 w-auto absolute left-50" v-motion :initial="{ y: 4000 }" :enter="{ y: 70, transition: { duration: 1000 } }" alt="Angry Vue" />

---
layout: intro
---

# Why choosing Vue?

---
layout: two-cols
heading: Why choosing Vue?
preload: false
---

<VClicks depth="2">

* Low Entry Barrier
  * SFCs only need HTML, CSS and JS knowledge to get started
* The golden middle between React and Angular in terms of freedom and opinions
  * Only little boilerplate and freedom to choose your own tools
  * Has one way (as we've seen) for important things like state management, routing, etc.
* Excellent documentation
* Amazing DevTools

</VClicks>

::right::

<div class="relative">

<Code class="absolute" v-click="2" v-click.hide="3" v-motion  :initial="{ x: 2000, opacity: 0 }" :click-2="{ x: 0, opacity: 1 }" :leave="{ x: 200, opacity: 0 }" file="example.vue">

```vue
<template>
  <div>Hello World</div>
  <p v-if="count % 2 === 0">Even</p>
  <p v-else>Odd</p>
  <button @click="count++">Increment</button>
  <p>Count: {{ count }}</p>
</template>

<script setup lang="ts">
import { ref } from 'vue'
const count = ref(0)
</script>

<style scoped>
p {
  color: red;
}
</style>
```

</Code>

<img v-click="4" v-click.hide="6" v-motion :initial="{ x: 2000, opacity: 0 }" :click-4="{ x: 0, opacity: 1 }" :leave="{ x: 200, opacity: 0 }" src="/react-angular-vue.svg" alt="React vs Angular vs Vue in terms of freedom" class="ml-32 h-90 absolute top-0">

<img v-click="7" v-motion :initial="{ x: 2000, opacity: 0 }" :click-6="{ x: 0, opacity: 1 }" :leave="{ x: 200, opacity: 0 }" src="https://devtools.vuejs.org/features/overview.png" alt="Vue Dev Tools" class="absolute top-0">

</div>

---
layout: intro
---

# But the job market?!

---
layout: intro
---

# We are <span class="underline text-yellow-500">Frontend</span> developers

---
layout: intro
---

# But the ecosystem!?

---

# What libraries are you missing?

<VClicks depth="2">

* Gazillion component/ui libraries available
  * Nuxt UI, Vuetify, PrimeVue, Radix Vue (Reka UI), Shadcn Vue, Inspira UI (Aceternity/Magic UI), ...
* TanStack Query?
  * There is [TanStack Query Vue](https://tanstack.com/query/latest/docs/framework/vue/overview)!
* Animation?
  * [Motion Vue](https://motion.dev/docs/vue) (fka Framer Motion)
* 3D?
  * [Tres.js](https://tresjs.org/)
* Form Handling?
  * [FormKit](https://formkit.com/), [VueForm](https://vueform.com/)
* Utils?
  * [VueUse](https://vueuse.org/)

</VClicks>

---
layout: intro
---

# Does it have Signals?!

---

# Does it have Signals?!

<VClicks depth="2">

* **Yes, it does!**
* No getter/setter but mutable state
* `ref` holding the reactive reference and is deeply reactive
  * Can be top-level reactive only via `shallowRef`
* `computed` holding the derived state
* `watch`/`watchEffect` for side effects

</VClicks>

---
layout: intro
---

# But is it performant?

---

# But is it performant?

<div class="flex gap-8">
<VClicks>

<img class="h-110" src="/vue-comparison-1.jpg" alt="Performance chart">
<img class="h-110" src="/vue-comparison-2.jpg" alt="Performance chart">
<img class="h-110" src="https://pbs.twimg.com/media/GowmkHAbUAAVrYG?format=jpg&name=large" alt="Performance chart">

</VClicks>
</div>

---
layout: intro
---

# Vue 3.6

---
layout: intro
---

# Alien Signals port to Vue

---

# Alien Signals

<VClicks>

* Project from Johnson Chu (known for e.g. Volar)
* Needed a faster signal library
* "Accidentally" created the fastest Signal library on the planet
* **-14% memory usage** and up to **30x perf boost** compared to current implementation
* Was ported to other languages (dart, lua, ...)
* Improvements can also benefit other frameworks ([not only Vue](https://github.com/vuejs/core/pull/12349))
* [Experimental PR to improve the official Polyfill](https://github.com/proposal-signals/signal-polyfill/pull/44)

</VClicks>

---

# Signal Lib Performance Comparison

<img src="/signal-perf.png" alt="Signal Performance chart" class="filter dark:filter-invert mx-auto h-85">
<div class="mx-auto text-center"><a class="text-xs" href="https://github.com/transitive-bullshit/js-reactivity-benchmark">Source</a>
</div>

---
layout: intro
---

# Vapor Mode

---

# Vapor Mode (experimental)

<VClicks>

* Opt-in
* No VDOM anymore
* `<script vapor>`
* Vapor-only possible too!
* No feature-parity yet (Suspense, KeepAlive, SSR Hydration, Transition Support, etc.)

</VClicks>

---

# Vapor as Compile Target?

<VClicks>

* kazupon working on [`inclusion-vapor`](https://github.com/kazupon/inclusion-vapor)
* What if Vapor would be a compile target? ([Daniel Roe, DejaVue #E044](https://share.transistor.fm/s/3c5bc972))
* Could bring real framework interoperability and move them closer together

</VClicks>

---
layout: intro
---

## But back to the questions you might have...

---
layout: intro
---

# Only one file per component?

---
layout: intro
---

# Vue Vine

---

# Vue Vine

* "Finally" a way to solve a pet peeve of many Vue developers

<VClicks>

* Multiple components in one file, while keeping the Vue Template syntax
* Extra library and opt-in (not part of Vue core)
* Will continue to evolve

</VClicks>

<Code v-click file="test.vine.ts">

````md magic-move {at: 5}
```ts
function MyComponent() {
  return vine`<div>Hello World</div>`
}

// This is also valid
const AnotherComponent = () => vine`<div>Hello World</div>`
```
```ts

function MyComponent() {
  return vine`<div>Hello World</div>`
}

// This is also valid
const AnotherComponent = () => vine`<MyComponent />`
```
````

</Code>

---

# The Meta Framework

<div class="space-y-8">
<VClicks>

> It's easier than ever to learn a new framework, and there's [...] less reason than ever to learn a new framework if you're really good at one.

> **The biggest reason to change is the meta framework**. The meta framework is where [...] all of the new important stuff is happening.

> So it's more **important to pick a meta framework you like** than [...] which front end framework you want. 

</VClicks>
</div>

<div v-click class="flex flex-col mt-8 items-center">
<img src="https://avatars.githubusercontent.com/u/1950463?v=4" alt="Justin Schroeder" class="h-20 w-20 rounded-full mx-auto">
<a class="text-xs mt-2" href="https://share.transistor.fm/s/39e69889#t=13m13s">Justin Schroeder in DejaVue #E045</a>
</div>

<style>
  p {
    @apply text-xl;
  }
</style>

---
layout: intro
---

# What makes Nuxt.js special?

---

# What makes Nuxt.js special?


<VClicks>

* Use any kind of rendering strategy (SSR, SSG, CSR, ...) per route
* Server Components (nope, no "Vue Server Components" ever!)
* Deploy wherever you want - no vendor lock-in
* DX improvements and optimizations
* Powerful DevTools
* ...and much more!

</VClicks>

---
layout: intro
---

# So, what will come to Nuxt.js in the future?

Here are some ideas... (NOT "officially" confirmed)

---

# Future Features

<VClicks>

* SSR Streaming
* Better E2E typesafety (typed query params and body)
* Improved route groups features
* Runtime Config and Env validation
* Service Worker layers
* Devtools supporting a11y and perf hints + **fixes**
* Better AI support (hey llms.txt)
* Security improvements (e.g. including [CSP generation](https://github.com/nuxt/nuxt/discussions/30404))
* And many more improvements (perf, DX, and so on)

</VClicks>

---
layout: intro
---

# Rustification

---
layout: two-cols
heading: Rustification - Rolldown
---

<VClicks depth="2">

* Rust-based rollup-compatible bundler
* Combining the best of the previous tools
  * Speed of esbuild
  * Simple & Flexible Rollup Plugin API & Ecosystem
  * Advanced features for optimization that webpack offers
* Drop-in pkg for `vite` called `rolldown-vite`
* [Beta already available](https://vite.dev/rolldown)
* [2-16x faster builds](https://github.com/vitejs/rolldown-vite-perf-wins)

</VClicks>

::right::

<div class="h-100 flex justify-center items-center">
  <div class="relative flex justify-center items-center">
    <div class="absolute inset-0 rounded-full blur-2xl" style="background: radial-gradient(circle at 50% 50%, #f2ce49 0%, #fd6f1c 60%, transparent 100%); z-index: 0;"></div>
    <VoidzeroIconsRolldown class="h-32 w-32 relative z-10" />
  </div>
</div>

---

# Phases of `rolldown-vite`

<VClicks>

0. Shadow-dropping the package (done!)
1. Official Announcement of `rolldown-vite` (soon)
2. Merge of `rolldown-vite` and `vite`
3. Full Bundle Mode by Default (will be testable earlier)

</VClicks>

---
layout: intro
---

# Why Full Bundle Mode?

---

# Why Full Bundle Mode?

<VClicks depth="2">

* Vite's unbundled dev server is fast but not free of problems
  * Dev/Prod inconsistency causing hard-to-debug issues
  * Performance hits in large apps due to many network requests
* Full Bundle Mode benefits
  * Faster startup for large apps
  * Consistent dev/prod behavior
  * Fewer network requests during dev
  * Efficient HMR with ESM

</VClicks>

---
layout: two-cols
heading: Rustification - Oxc
---


<VClicks>

* Rust-based compiler for JavaScript and TypeScript
* Parser, Linter, Formatter, Transformer, and way more
* Is [adopted](https://github.com/vitest-dev/vitest/pull/7609) [more](https://github.com/unjs/unenv/pull/417) [and](https://github.com/react-querybuilder/react-querybuilder/pull/778) [more](https://github.com/intlify/vue-i18n/pull/2067) [throughout](https://github.com/tamagui/tamagui/commit/33376ecb50b9f23eab175925dd8b79983a667ba9) the ecosystem
* Powers Rolldown but can be used standalone too

</VClicks>

::right::

<div class="h-100 flex justify-center items-center">
  <div class="relative flex justify-center items-center">
    <div class="absolute inset-0 rounded-full blur-2xl" style="background: radial-gradient(circle at 50% 50%, #91ede9 0%, #2b3c5a 60%, transparent 100%); z-index: 0;"></div>
    <VoidzeroIconsOxc class="h-32 w-32 relative z-10" />
  </div>
</div>

---

# Oxlint

<VClicks>

* In Beta
* Can be used to replace ESLint (fully and partially) - **50x to 100x faster**
* **More than 500 rules** included at the moment
* Migration script to migrate away from ESLint
* ESLint plugin to disable all rules that are enabled in Oxlint
* We need [your input on JavaScript Lint Plugins](https://github.com/oxc-project/oxc/discussions/10342)

</VClicks>

---

# `oxc-minify`

<VClicks>

* Used in Rolldown as default minifier
* Already outperforms esbuild in speed and time
* [Benchmark](https://github.com/privatenumber/minification-benchmarks#%EF%B8%8F-minifier-showdown)

</VClicks>

---


<div>

| Artifact                                                                                                                               |                   Original size |                         Gzip size |                                   |
| :------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------: | --------------------------------: | --------------------------------: |
| [typescript v4.9.5](https://www.npmjs.com/package/typescript/v/4.9.5) ([Source](https://unpkg.com/typescript@4.9.5/lib/typescript.js)) |                      `10.95 MB` |                         `1.88 MB` |                                   |
| **Minifier**                                                                                                                           |               **Minified size** |                **Minzipped size** |                          **Time** |
| 1. [@swc/core](packages/minifiers/minifiers/swc.ts)                                                                                    | **<sup>🏆-70% </sup>`3.31 MB`** | **<sup>🏆-54% </sup>`859.20 kB`** |        <sup>*8x* </sup>`2,120 ms` |
| 2. [oxc-minify](packages/minifiers/minifiers/oxc-minify.ts)                                                                            |       <sup>-69% </sup>`3.35 MB` |       <sup>-54% </sup>`860.66 kB` |          <sup>*1x* </sup>`439 ms` |
| 3. [@tdewolff/minify](packages/minifiers/minifiers/tdewolff-minify.ts)                                                                 |       <sup>-69% </sup>`3.35 MB` |       <sup>-54% </sup>`875.82 kB` |        **<sup>🏆 </sup>`254 ms`** |
| 4. [uglify-js (no compress)](packages/minifiers/minifiers/uglify-js.ts)                                                                |       <sup>-68% </sup>`3.54 MB` |       <sup>-53% </sup>`876.54 kB` |       <sup>*15x* </sup>`4,029 ms` |
| 5. [terser (no compress)](packages/minifiers/minifiers/terser.ts)                                                                      |       <sup>-68% </sup>`3.53 MB` |       <sup>-53% </sup>`879.30 kB` |       <sup>*20x* </sup>`5,318 ms` |
| 6. [esbuild](packages/minifiers/minifiers/esbuild.ts)                                                                                  |       <sup>-68% </sup>`3.49 MB` |       <sup>-51% </sup>`915.55 kB` |          <sup>*1x* </sup>`484 ms` |
| 12. [bun](packages/minifiers/minifiers/bun.ts) <sub title="Failed: post-validation">❌ Post-validation</sub>                            |                               ❌ |                                ❌  |                                 - |
</div>

---
layout: intro
---

# TL;DR?

---

# TL;DR?

<VClicks>

* Vue is boring and that's good
* It is a great fit for your next project (change my mind!)
* Stable core, more "experimentation" in the ecosystem
* Frameworks converging, meta frameworks often make the difference
* Rustification of modern JavaScript tooling will change a lot
  * No matter which framework you use <sup class="-ml-1">*</sup>

</VClicks>

<p v-click="4" class="text-[8pt] mt-32 text-right"><sup>*</sup> Except Next.js</p>

---

## Ready for more? Then <span class="inline-block bg-gradient-to-r from-blue-600 via-red-500 to-green-400 bg-clip-text text-transparent">follow</span> along!

<div class="flex mx-32 mt-16 gap-8 my-auto justify-around items-center">
  <Qrcode v-click class="max-w-xl" url="https://www.youtube.com/@TheAlexLichter/">
    YouTube
    <span class="text-sm text-gray-500">lichter.link/yt</span>
  </Qrcode>
  <Qrcode v-click class="max-w-xl" url="https://dejavue.fm/?ref=vuejsde2024">
    The DejaVue Podcast
    <span class="text-sm text-gray-500">dejavue.fm</span>
  </Qrcode>
</div>

---
layout: intro
---

# Thanks a lot to my sponsors!
<img src="https://raw.githubusercontent.com/TheAlexLichter/static/main/sponsors.svg" class="h-80 mx-auto" alt="My GitHub sponsors">

---
layout: two-cols
heading: Thank you for your attention!
---

<template v-slot:default>
<div class="flex flex-col justify-center items-center h-full">
<img
  class="w-75 rounded-full"
  src="https://lichter.io/img/me@2x.webp"
  />
  <h2 class="mt-4">Alexander Lichter</h2>
</div>
</template>

<template v-slot:right>

* <VoidzeroIconsVoidzeroLogo class="text-white" width="4rem" height="auto" /> DevRel
* <mdi-account-check class="dark:text-green-100 text-green-700" /> Web Engineering Consultant
* <mdi-microphone /> Speaker & Instructor
* <logos-nuxt-icon /> Nuxt.js Team
* <mdi-github /><logos-bluesky class="text-sm mb-1 text-blue-400" /><mdi-youtube class="text-red-500" /><mdi-twitch class="text-purple-700" /> @TheAlexLichter
* <mdi-web /> [https://lichter.io](https://lichter.io)

</template>

<style>
  ul {
    @apply space-y-2 mt-10 text-xl h-full;
  }
</style>