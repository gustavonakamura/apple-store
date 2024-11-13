<template>
    <header class="bg-gray-800 text-white p-4">
        <nav class="flex justify-between">
            <router-link to="/" class="text-lg font-bold">Loja Apple</router-link>
            <div class="flex space-x-4">
                <router-link to="/add-item" class="hover:text-gray-300">Cadastrar Novo produto da Apple</router-link>
                <router-link to="/items" class="hover:text-gray-300">Listar produtos da Apple</router-link>
            </div>
        </nav>
    </header>
</template>


<script>
export default {
    name: "AppHeader",
};
</script>

<style scoped>
/* Estilos para o cabeçalho */
</style>