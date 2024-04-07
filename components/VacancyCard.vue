<template>
    <div class="max-w-sm rounded overflow-hidden shadow-lg">
        <div class="px-6 py-4">
            <div class="">
                <p class="text-xl font-medium text-black"><NuxtLink :to="`/vacancy/${vacancy.id}`">{{vacancy.name}}</NuxtLink></p>
                <p class="my-4">{{ vacancy.salary }}</p>
                <p>{{ vacancy.description }}</p>
            </div>
        </div>
    </div>
</template>

<script setup>

const { vacancy } = defineProps(['vacancy'])

</script>

<style scoped>

</style>