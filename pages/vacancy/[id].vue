<template>
    <div>
        <p>{{ vacancy.name }}</p>
        <p>{{ vacancy.salary }}</p>
        <p>{{ vacancy.description }}</p>
    </div>
</template>

<script setup>
    const { id } = useRoute().params;
    console.log(id);

    const uri = 'http://vacancy-api.loc/index.php?r=vacancy/view&id=' + id;

    const { data: vacancy } = await useFetch(uri);

</script>

<style scoped>

</style>