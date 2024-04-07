<template>
    <div>
        <header class="shadow-sm bg-white">
            <nav class="container p-4 flex justy-beetwen">
                <ul class="flex gap-2">
                    <li class="btn"><NuxtLink to="/vacancy/">Список вакансий</NuxtLink></li>
                    <li><NuxtLink to="/vacancy/create">Добавить</NuxtLink></li>
                </ul>
            </nav>
        </header>
    </div>
    <div class="container mx-auto p-4">
        <slot />
    </div>
</template>

<style scoped>
    .router-link-exact-active {
        color: #81bb3c;
    }
</style>