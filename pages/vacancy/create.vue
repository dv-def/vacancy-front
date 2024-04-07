<template>
    <div>
        <h2>Добавление вакансии</h2>
        <form @submit.prevent="submitForm">
            <label>Название</label>
            <input v-model="form.name" type="text"/>

            <label>Зарплата</label>
            <input v-model="form.salary" type="number"/>
            
            <label>Описание</label>
            <input v-model="form.description" type="text"/>
            
            <button 
                type="submit">
                Сохранить
            </button>
        </form>
    </div>
</template>

<script setup>
    
    const form = {
        name: '',
        salary: 0,
        description: ''
    };

    function submitForm() {
        const uri = 'http://vacancy-api.loc/vacancy/create';
        
        $fetch(uri, {
            method: 'POST',
            body: form,
        });

    }

</script>

<style scoped>

</style>