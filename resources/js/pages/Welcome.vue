<script setup lang="ts">
import { Head, Link } from '@inertiajs/vue3';
import { login, logout, register } from '@/routes';

interface Project {
    name: string;
    description: string;
    tags: string[];
    url: string;
}

const projects: Project[] = [
    {
        name: 'Chess engine',
        description: 'A chess engine written from scratch in PHP, with a Vue and Inertia interface for playing against it in the browser.',
        tags: ['Laravel', 'Vue', 'Inertia', 'Tailwind'],
        url: 'https://chess.matthijs.bio',
    },
    {
        name: 'Game Boy Color emulator',
        description: 'A Game Boy Color emulator written in TypeScript, backed by a small Laravel API that syncs save states across devices.',
        tags: ['TypeScript', 'Laravel','Inertia', 'Tailwind'],
        url: 'https://gameboy.matthijs.bio',
    },
    {
        name: 'Decodive',
        description: 'A peer-to-peer marketplace where people rent or sell event and festival decorations, complete with in-app messaging and paid listing promotion.',
        tags: ['TypeScript', 'Vue', 'Laravel', 'Inertia', 'Tailwind', 'Filament'],
        url: 'https://decodive.nl'
    }
];

const skills: string[] = [
    'PHP / Laravel',
    'Vue',
    'Inertia',
    'TypeScript',
    'Tailwind CSS',
    'Statamic',
    'Docker',
    'Git / GitHub',
    'MySQL / MariaDB',
];
</script>

<template>
    <Head title="Portfolio" />

    <div class="min-h-screen bg-[#FDFDFC] text-[#1b1b18] dark:bg-[#0a0a0a] dark:text-[#EDEDEC]">
        <header class="mx-auto flex max-w-4xl items-center justify-between gap-3 p-4 sm:p-6 lg:p-8">
            <span class="truncate text-base font-semibold sm:text-lg">Matthijs Bedaf</span>
        </header>

        <main class="mx-auto max-w-4xl px-6 lg:px-8">
            <section class="py-16 lg:py-24">
                <h1 class="text-4xl font-bold tracking-tight lg:text-5xl">
                    Hi, I'm Matthijs.
                </h1>
                <p class="mt-4 max-w-2xl text-lg text-[#706f6c] dark:text-[#A1A09A]">
                    I'm a full-stack developer who builds web apps with Laravel
                    and Vue. In my spare time I like taking on problems that
                    aren't strictly necessary, a chess engine, a Game Boy
                    emulator just to see how they work from the inside.
                </p>
                <div class="mt-8 flex flex-wrap gap-4 text-sm">
                    <a
                        href="mailto:matthijsbedaf05@gmail.com"
                        class="rounded-sm bg-[#1b1b18] px-5 py-2 font-medium text-white hover:opacity-90 dark:bg-[#EDEDEC] dark:text-[#1b1b18]"
                    >
                        Get in touch
                    </a>
                    <a
                        href="https://github.com/rocky9878"
                        target="_blank"
                        class="rounded-sm border border-[#19140035] px-5 py-2 hover:border-[#1915014a] dark:border-[#3E3E3A] dark:hover:border-[#62605b]"
                    >
                        GitHub
                    </a>
                </div>
            </section>

            <section class="border-t border-[#19140015] py-16 dark:border-[#FFFFFF10]">
                <h2 class="text-2xl font-semibold">Projects</h2>
                <p class="mt-2 text-sm text-[#706f6c] dark:text-[#A1A09A]">
                    Log in to try the full versions with saved progress.
                </p>
                <div class="mt-6 grid gap-6 sm:grid-cols-2 lg:grid-cols-3">
                    <a
                        v-for="project in projects"
                        :key="project.name"
                        :href="project.url"
                        class="group rounded-lg border border-[#19140015] p-5 transition hover:border-[#1915014a] dark:border-[#FFFFFF10] dark:hover:border-[#62605b]"
                    >
                        <h3 class="font-medium group-hover:underline">{{ project.name }}</h3>
                        <p class="mt-2 text-sm text-[#706f6c] dark:text-[#A1A09A]">
                            {{ project.description }}
                        </p>
                        <div class="mt-4 flex flex-wrap gap-2">
                            <span
                                v-for="tag in project.tags"
                                :key="tag"
                                class="rounded-full bg-[#1914030a] px-2.5 py-0.5 text-xs dark:bg-[#FFFFFF10]"
                            >
                                {{ tag }}
                            </span>
                        </div>
                    </a>
                </div>
            </section>

            <section class="border-t border-[#19140015] py-16 dark:border-[#FFFFFF10]">
                <h2 class="text-2xl font-semibold">Skills</h2>
                <ul class="mt-6 flex flex-wrap gap-3">
                    <li
                        v-for="skill in skills"
                        :key="skill"
                        class="rounded-sm border border-[#19140015] px-3 py-1.5 text-sm dark:border-[#FFFFFF10]"
                    >
                        {{ skill }}
                    </li>
                </ul>
            </section>
        </main>
    </div>
</template>
