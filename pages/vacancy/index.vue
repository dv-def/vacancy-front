<template>
    <div class="card">
        <div v-for="v in vacancies">
            <NuxtLink :to="`/vacancy/${v.id}`">{{v.name}}</NuxtLink>
            <p>{{v.salary}}</p>
            <p>{{v.description}}</p>
        </div>
    </div>
    
</template>

<script setup>
    const uri = 'http://vacancy-api.loc/index.php?r=vacancy/index';

    const { data: vacancies } = await useFetch(uri);
</script>

<style scoped>

</style>