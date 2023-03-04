<template>
    <Head title="Projects Index" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Projects</h2>
        </template>

        <div class="py-12">


            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="flex justify-end m-2 p-2">
                    <Link :href="route('projects.create')"
                          class="px-4 py-2 bg-green-500 hover:bg-green-700 text-white rounded-md"
                          method="get"
                          as="button">New Project</Link>

                </div>
                <div class="overflow-hidden shadow-sm sm:rounded-lg">
                    <p>Todo: Display Project Table Here</p>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>

</template>

<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head, Link } from '@inertiajs/vue3';
</script>
