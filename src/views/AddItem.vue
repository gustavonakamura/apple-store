<template>
    <div>
        <Header />
        <h1>Adicionar Novo produto da Apple</h1>
        <ItemForm @add-item="handleAddItem" />
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