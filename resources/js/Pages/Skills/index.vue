<template>
    <Head title="Skills Index" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Skills</h2>
        </template>

        <div class="py-12">


            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="flex justify-end m-2 p-2">
                        <Link :href="route('skills.create')"
                              class="px-4 py-2 bg-indigo-500 hover:bg-indigo-700 text-white rounded-md"
                              method="get"
                              as="button">New Skill</Link>

                    </div>
                </div>

                <div class="display_table mt-5">

                    <div class="relative overflow-x-auto" v-if="skills.data.length> 0">
                        <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400">
                            <thead class="text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-gray-400">
                            <tr>

                                <th scope="col" class="px-6 py-3">
                                    Name
                                </th>
                                <th scope="col" class="px-6 py-3">
                                    Image URL
                                </th>
                            </tr>
                            </thead>
                            <tbody>

                            <tr v-for="skill in skills.data" :key="skill.id"
                                class="bg-white border-b dark:bg-gray-800 dark:border-gray-700">
                                <td  class="px-6 py-4"> {{skill.name}}</td>
                                <td  class="px-6 py-4">
<!--                                    {{skill.image}}-->
                                  <img :src="skill.image" class="w-12 h-12 rounded" />
                                </td>

                            </tr>

                            </tbody>
                        </table>
                    </div>

                    <div v-else>
                        <p>No Skill(s) found</p>

                    </div>

                </div>
            </div>
        </div>
    </AuthenticatedLayout>

</template>

<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head, Link } from '@inertiajs/vue3';

defineProps({
    'skills': Object
})


</script>
