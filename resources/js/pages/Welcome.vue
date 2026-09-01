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
        name: 'Project One',
        description: 'A short description of what this project does and why it matters.',
        tags: ['Laravel', 'Vue', 'Inertia'],
        url: '#',
    },
    {
        name: 'Project Two',
        description: 'A short description of what this project does and why it matters.',
        tags: ['TypeScript', 'Tailwind'],
        url: '#',
    },
    {
        name: 'Project Three',
        description: 'A short description of what this project does and why it matters.',
        tags: ['PHP', 'PostgreSQL'],
        url: '#',
    },
];

const skills: string[] = [
    'PHP / Laravel',
    'Vue',
    'Inertia',
    'TypeScript',
    'Tailwind CSS',
    'AI assisted development',
    'Docker',
];
</script>

<template>
    <Head title="Portfolio" />

    <div class="min-h-screen bg-[#FDFDFC] text-[#1b1b18] dark:bg-[#0a0a0a] dark:text-[#EDEDEC]">
        <header class="mx-auto flex max-w-4xl items-center justify-between p-6 lg:p-8">
            <span class="text-lg font-semibold">Matthijs bedaf</span>
            <nav class="flex items-center gap-4 text-sm">
                <template v-if="$page.props.auth.user">
                    <Link
                        :href="logout()"
                        class="rounded-sm border border-[#19140035] px-5 py-1.5 hover:border-[#1915014a] dark:border-[#3E3E3A] dark:hover:border-[#62605b]"
                    >
                        Log out
                    </Link>
                </template>
                <template v-else>
                    <Link
                        :href="login()"
                        class="rounded-sm border border-transparent px-5 py-1.5 hover:border-[#19140035] dark:hover:border-[#3E3E3A]"
                    >
                        Log in
                    </Link>
                    <Link
                        :href="register()"
                        class="rounded-sm border border-[#19140035] px-5 py-1.5 hover:border-[#1915014a] dark:border-[#3E3E3A] dark:hover:border-[#62605b]"
                    >
                        Register
                    </Link>
                </template>
            </nav>
        </header>

        <main class="mx-auto max-w-4xl px-6 lg:px-8">
            <section class="py-16 lg:py-24">
                <h1 class="text-4xl font-bold tracking-tight lg:text-5xl">
                    Hi, I'm Matthijs.
                </h1>
                <p class="mt-4 max-w-2xl text-lg text-[#706f6c] dark:text-[#A1A09A]">
                    I like making things!
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
                        class="rounded-sm border border-[#19140035] px-5 py-2 hover:border-[#1915014a] dark:border-[#3E3E3A] dark:hover:border-[#62605b]"
                    >
                        GitHub
                    </a>
                </div>
            </section>

            <section class="border-t border-[#19140015] py-16 dark:border-[#FFFFFF10]">
                <h2 class="text-2xl font-semibold">Projects</h2>
                <p class="pt-2 pl-4 text-white/60 text-sm">tip: login to access the full functionality!</p>
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
