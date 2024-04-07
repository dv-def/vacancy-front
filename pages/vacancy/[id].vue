<template>
    <div>
        <div class="max-w-sm rounded overflow-hidden shadow-lg px-2 py-2">
            <h1 class="text-xl font-medium text-black">{{ vacancy.name }}</h1>
            <p class="my-2">Зарплата: {{ vacancy.salary }}</p>
        </div>
        <p class="px-2 py-2">{{ vacancy.description }}</p>

    </div>
</template>

<script setup>
    const { id } = useRoute().params;

    const uri = 'http://vacancy-api.loc/index.php/vacancy/' + id;

    const { data: vacancy } = await useFetch(uri);

</script>

<style scoped>

</style>