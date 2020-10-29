<template>
    <div>
        <h2 class="h2">Home Page</h2>

        <p>Todos in next link</p>

        <router-link to="/todos" class="todos-link">Todos</router-link>
    </div>
</template>

<style scoped>
    .todos-link {
        text-decoration: none;
    }
</style>