<template>
    <div class="card">
        <p class="font-bold">{{ vacancy.name }}</p>
        <p class="font-bold">{{ vacancy.salary }}</p>
        <p class="font-bold">{{ vacancy.description }}</p>
    </div>
    <hr/>
</template>

<script setup>

const { vacancy } = defineProps(['vacancy'])

</script>

<style scoped>

</style>