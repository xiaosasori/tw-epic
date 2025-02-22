<script lang="ts" setup>
import { clsx } from '~/utlis'

const logos = [
  {
    src: 'logos:nuxt-icon',
    alt: 'Nuxt',
    href: 'https://nuxt.com',
    column: 1,
    row: 1,
  },
  {
    src: 'logos:fly',
    alt: 'Fly.io',
    href: 'https://fly.io',
    column: 1,
    row: 2,
  },
  {
    src: 'logos:sqlite',
    alt: 'SQLite',
    href: 'https://sqlite.org',
    column: 1,
    row: 3,
  },
  {
    src: 'logos:prisma',
    alt: 'Prisma',
    href: 'https://prisma.io',
    column: 2,
    row: 2,
  },
  { src: 'logos:zod', alt: 'Zod', href: 'https://zod.dev/', column: 2, row: 3 },
  {
    src: 'logos:github-icon',
    alt: 'GitHub',
    href: 'https://github.com',
    column: 2,
    row: 4,
  },
  {
    src: 'simple-icons:resend',
    alt: 'Resend',
    href: 'https://resend.com',
    column: 2,
    row: 5,
  },
  {
    src: 'logos:react-query-icon',
    alt: 'Tanstack Query',
    href: 'https://tanstack.com/query/latest/docs/framework/vue/overview',
    column: 2,
    row: 6,
  },
  {
    src: 'logos:tailwindcss-icon',
    alt: 'Tailwind CSS',
    href: 'https://tailwindcss.com',
    column: 3,
    row: 3,
  },
  {
    src: 'simple-icons:radixui',
    alt: 'Radix UI',
    href: 'https://www.radix-ui.com/',
    column: 3,
    row: 4,
  },
  {
    src: 'simple-icons:shadcnui',
    alt: 'shadcn/ui',
    href: 'https://ui.shadcn.com/',
    column: 3,
    row: 5,
  },
  {
    src: 'logos:playwright',
    alt: 'Playwright',
    href: 'https://playwright.dev/',
    column: 4,
    row: 1,
  },
  { src: 'logos:msw', alt: 'MSW', href: 'https://mswjs.io', column: 4, row: 2 },
  {
    src: 'logos:faker',
    alt: 'Faker.js',
    href: 'https://fakerjs.dev/',
    column: 4,
    row: 3,
  },
  {
    src: 'logos:vitest',
    alt: 'Vitest',
    href: 'https://vitest.dev',
    column: 4,
    row: 4,
  },
  {
    src: 'logos:testing-library',
    alt: 'Testing Library',
    href: 'https://testing-library.com',
    column: 4,
    row: 5,
  },
  {
    src: 'logos:docker-icon',
    alt: 'Docker',
    href: 'https://www.docker.com',
    column: 4,
    row: 6,
  },
  {
    src: 'logos:typescript-icon',
    alt: 'TypeScript',
    href: 'https://typescriptlang.org',
    column: 5,
    row: 2,
  },
  {
    src: 'logos:prettier',
    alt: 'Prettier',
    href: 'https://prettier.io',
    column: 5,
    row: 3,
  },
  {
    src: 'logos:eslint',
    alt: 'ESLint',
    href: 'https://eslint.org',
    column: 5,
    row: 4,
  },
  {
    src: 'logos:sentry',
    alt: 'Sentry',
    href: 'https://sentry.io',
    column: 5,
    row: 5,
  },
] as const

const columnClasses: Record<(typeof logos)[number]['column'], string> = {
  1: 'xl:col-start-1',
  2: 'xl:col-start-2',
  3: 'xl:col-start-3',
  4: 'xl:col-start-4',
  5: 'xl:col-start-5',
}
const rowClasses: Record<(typeof logos)[number]['row'], string> = {
  1: 'xl:row-start-1',
  2: 'xl:row-start-2',
  3: 'xl:row-start-3',
  4: 'xl:row-start-4',
  5: 'xl:row-start-5',
  6: 'xl:row-start-6',
}
</script>

<template>
  <ul
    class="flex max-w-3xl flex-wrap justify-center gap-2 sm:gap-4 xl:row-span-6 xl:grid xl:grid-flow-col xl:grid-cols-5 xl:grid-rows-subgrid"
  >
    <li
      v-for="(logo, index) in logos"
      :key="logo.alt"
      :style="{ '--loop-index': index }"
      :class="
        clsx(
          columnClasses[logo.column],
          rowClasses[logo.row],
          'animate-fade-in motion-safe:animate-roll-reveal',
          'motion-safe:[animation-delay:calc(0.07s*var(--loop-index))]',
        )
      "
    >
      <a
        :href="logo.href"
        class="bg-highlight/[7%] hover:bg-highlight/10 focus:ring-highlight grid size-20 place-items-center rounded-2xl p-4 transition hover:-rotate-6 focus:ring-2 focus:ring-offset-2 focus:outline-none sm:size-24"
      >
        <Icon class="size-full" :name="logo.src" :atl="logo.alt" />
      </a>
    </li>
  </ul>
</template>
