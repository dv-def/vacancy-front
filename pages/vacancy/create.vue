<template>
    <form class="max-w-sm mx-auto" @submit.prevent="submitForm">
        <div class="mb-5">
            <h1>Добавление вакансии</h1>
        </div>
        <div class="mb-5">
            <label class="form-label">Название</label>
            <input class="form-input" v-model="form.name" type="text" required>
        </div>
        <div class="mb-5">
            <label class="form-label">Зарплата</label>
            <input class="form-input" v-model="form.salary" type="number" required/>
        </div>
        <div class="mb-5">
            <label class="form-label">Описание</label>
            <input class="form-input"v-model="form.description" type="text" required/>
        </div>
        <button 
            class="form-btn"
            type="submit">
            Сохранить
        </button>
    </form>
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
        }).then(function(result) {
            if (result['success']) {
                alert('Вакансия успешно создана');
                navigateTo('/vacancy')
            } else {
                alert('При создании вакансии порищолша ошибка');
            }
        });
    }

</script>

<style scoped>

</style>