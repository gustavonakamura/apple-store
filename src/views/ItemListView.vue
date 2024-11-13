<template>
    <div>
        <Header />
        <h1>Lista de Produtos da Apple</h1>
        <ItemList :items="items" @delete-item="handleDeleteItem" />
        <Footer />
    </div>
</template>

<script>
import Header from "../components/AppHeader.vue";
import Footer from "../components/AppFooter.vue";
import ItemList from "../components/ItemList.vue";

export default {
    components: { Header, Footer, ItemList },
    data() {
        return {
            items: JSON.parse(localStorage.getItem("items")) || [],
        };
    },
    methods: {
        handleDeleteItem(index) {
            this.items.splice(index, 1);
            localStorage.setItem("items", JSON.stringify(this.items));
        },
    },
};
</script>