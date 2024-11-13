<template>
    <div class="min-h-screen bg-gray-100 flex flex-col">
        <Header />
        <main class="flex-grow flex items-center justify-center p-6">
            <div class="w-full max-w-lg bg-white rounded-lg shadow-lg p-8">
                <h1 class="text-2xl font-semibold text-gray-800 mb-6 text-center">Adicionar Novo Produto da Apple</h1>
                <ItemForm @add-item="handleAddItem" />
            </div>
        </main>
        <Footer />
    </div>
</template>

<script>
import Header from "../components/AppHeader.vue";
import Footer from "../components/AppFooter.vue";
import ItemForm from "../components/ItemForm.vue";

export default {
    components: { Header, Footer, ItemForm },
    methods: {
        handleAddItem(item) {
            const storedItems = JSON.parse(localStorage.getItem("items")) || [];
            storedItems.push(item);
            localStorage.setItem("items", JSON.stringify(storedItems));
            this.$router.push("/items");
        },
    },
};
</script>

<style scoped>
/* Optional scoped styling for finer control if needed */
</style>
