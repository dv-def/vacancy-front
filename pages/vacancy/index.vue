<template>
    <div class="grid grid-cols-6">
        <div>Сортировать по:</div>
        <button @click="sortBySalary">
            Зарплате 
        </button>
        <button @click="sortByDate">
            Дате
        </button>
    </div>
    <div class="grid grid-cols-3 my-4">
        <div v-for="v in vacancies">
            <VacancyCard :vacancy="v"/>
        </div>
    </div>

    <div class="grid grid-cols-6">
        <button @click="prev">Prev</button>
        <button @click="next">Next</button>
    </div>
    
</template>

<script setup>
    const page = ref(1)
    const sort = ref('');

    const uri = 'http://vacancy-api.loc/vacancy/index';
    const { data: vacancies} = await useFetch(uri, {
        params: {
            page: page,
            sort: sort
        }
    }, {
        watch: [page, sort]
    });

    function prev() {
        page.value--
    }

    function next() {
        page.value++
    }

    function sortBySalary() {
        if (sort.value == '') {
            sort.value = 'salary';
        }

        if (!sort.value.startsWith('-')) {
            sort.value = '-salary';
        } else {
            sort.value = 'salery';
        }
    }

    function sortByDate() {
        if (sort.value == '') {
            sort.value = 'created_at';
        }

        if (!sort.value.startsWith('-')) {
            sort.value = '-created_at';
        } else {
            sort.value = 'created_at';
        }
    }

</script>

<style scoped>

</style>